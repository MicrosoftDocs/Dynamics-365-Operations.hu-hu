---
title: ER modell-leképezés kezelése külön ER-konfigurációkban
description: Ez a témakör ismerteti az Elektronikus jelentés (ER) modell-leképezések kezelésének módját a különböző ER-konfigurációk között.
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
ms.openlocfilehash: 2f1013cfc9f421525fb0661cd5ace5eeaa157f9a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093798"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="b5c5a-103">ER modell-leképezés kezelése külön ER-konfigurációkban</span><span class="sxs-lookup"><span data-stu-id="b5c5a-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5c5a-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="b5c5a-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="b5c5a-105">Ebben a feladat-útmutatóban létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő feladat-útmutató lépéseit kell végrehajtani: „ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, "ER Create a configuration provider" and mark it as active.</span></span> 

<span data-ttu-id="b5c5a-106">Mivel az ER-konfigurációk meg vannak osztva a vállalatok között, a feladat-útmutatót a tetszése szerint vállalat-adatkészlettel hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="b5c5a-107">A Feladat útmutató a funkcionalitása akkor érhető el, ha telepítette a következő gyorsjavítások valamelyikét: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 a Dynamics AX 7.0-s verzióhoz vagy https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 a Dynamics 365 for Operations verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="b5c5a-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="b5c5a-109">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="b5c5a-110">Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” feladat-útmutatóban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-110">If you don't see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider, and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="b5c5a-111">Új ER-modellkonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b5c5a-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="b5c5a-112">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="b5c5a-113">Új modellkonfiguráció hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-113">Add a new model configuration.</span></span> <span data-ttu-id="b5c5a-114">A névnek egyedinek kell lennie a konfigurációfában.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="b5c5a-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="b5c5a-116">A Név mezőben írja be a „Minta adatmodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="b5c5a-117">Minta adatmodell</span><span class="sxs-lookup"><span data-stu-id="b5c5a-117">Sample data model</span></span>  
4. <span data-ttu-id="b5c5a-118">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-118">Click Create configuration.</span></span>
5. <span data-ttu-id="b5c5a-119">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-119">Click Designer.</span></span>
6. <span data-ttu-id="b5c5a-120">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="b5c5a-121">A Név mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="b5c5a-122">Gyökér</span><span class="sxs-lookup"><span data-stu-id="b5c5a-122">Root</span></span>  
8. <span data-ttu-id="b5c5a-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-123">Click Add.</span></span>
9. <span data-ttu-id="b5c5a-124">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="b5c5a-125">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="b5c5a-126">Cég</span><span class="sxs-lookup"><span data-stu-id="b5c5a-126">Company</span></span>  
11. <span data-ttu-id="b5c5a-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-127">Click Add.</span></span>
12. <span data-ttu-id="b5c5a-128">A Leírás mezőben adja meg 'A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben' szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="b5c5a-129">A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="b5c5a-130">Kattintson a Gyökérhivatkozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-130">Click Root reference.</span></span>
14. <span data-ttu-id="b5c5a-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-131">Click OK.</span></span>
15. <span data-ttu-id="b5c5a-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-132">Click Save.</span></span>
16. <span data-ttu-id="b5c5a-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-133">Close the page.</span></span>
17. <span data-ttu-id="b5c5a-134">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-134">Click Change status.</span></span>
18. <span data-ttu-id="b5c5a-135">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-135">Click Complete.</span></span>
19. <span data-ttu-id="b5c5a-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="b5c5a-137">Új ER-modellhozzárendeléskonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b5c5a-137">Add a new ER model-mapping configuration</span></span>
1. <span data-ttu-id="b5c5a-138">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="b5c5a-139">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="b5c5a-140">A Név mezőbe írja be a „Minta hozzárendelés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="b5c5a-141">Minta leképezés</span><span class="sxs-lookup"><span data-stu-id="b5c5a-141">Sample mapping</span></span>  
4. <span data-ttu-id="b5c5a-142">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-142">Click Create configuration.</span></span>
5. <span data-ttu-id="b5c5a-143">Bontsa ki az Előfeltételek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="b5c5a-144">Az Implementációk előfeltételcsoport automatikusan hozzá van adva.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-144">The Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="b5c5a-145">A csoport tartalmazza a szülő adatmodell-konfigurációra hivatkozó előfeltétel-ellenőrzési összetevőt, és Implementációként van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="b5c5a-146">Ez azt jelenti, hogy ez a Mintahozzárendelés modellhozzárendelési konfiguráció a Minta adatmodell implementációjának minősül.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-146">This means that this Sample-mapping model-mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="b5c5a-147">Ezért ez az összetevő arra kényszeríti az ER-t, hogy mindig letöltse egy ER-tárházból a Minta-hozzárendelés modell-hozzárendelési konfigurációt, amikor letölti a Minta adatmodell modellkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-147">Therefore, this component will force ER to download the model-mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="b5c5a-148">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-148">Click Designer.</span></span>
    * <span data-ttu-id="b5c5a-149">A létrehozott modell-hozzárendelési konfiguráció egy új, üres hozzárendelést tartalmaz, amelynek a neve azonos a létrehozott konfiguráció nevével.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-149">The created model-mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="b5c5a-150">Ha egy kijelölt szülő modellkonfiguráció modell-hozzárendeléseket tartalmaz, ha azok át lesznek másolva egy új modell-hozzárendelési konfigurációba.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-150">When a selected parent model configuration contains model mappings, they will be copied to a new model-mapping configuration.</span></span>   
7. <span data-ttu-id="b5c5a-151">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-151">Click Designer.</span></span>
8. <span data-ttu-id="b5c5a-152">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="b5c5a-153">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-153">Click Add root.</span></span>
10. <span data-ttu-id="b5c5a-154">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="b5c5a-155">Cég</span><span class="sxs-lookup"><span data-stu-id="b5c5a-155">Company</span></span>  
11. <span data-ttu-id="b5c5a-156">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="b5c5a-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="b5c5a-157">CompanyInfo</span></span>  
12. <span data-ttu-id="b5c5a-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-158">Click OK.</span></span>
13. <span data-ttu-id="b5c5a-159">A fastruktúrában bontsa ki ezt: „Company”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="b5c5a-160">A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="b5c5a-161">A fastruktúrában válassza ki ezt: „Company\find()\Name”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="b5c5a-162">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-162">Click Bind.</span></span>
17. <span data-ttu-id="b5c5a-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-163">Click Save.</span></span>
18. <span data-ttu-id="b5c5a-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-164">Close the page.</span></span>
19. <span data-ttu-id="b5c5a-165">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-165">Close the page.</span></span>
20. <span data-ttu-id="b5c5a-166">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="b5c5a-167">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-167">Click User parameters.</span></span>
22. <span data-ttu-id="b5c5a-168">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="b5c5a-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-169">Click OK.</span></span>
24. <span data-ttu-id="b5c5a-170">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-170">Click Edit.</span></span>
25. <span data-ttu-id="b5c5a-171">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="b5c5a-172">Új ER-formátum hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b5c5a-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="b5c5a-173">A fastruktúrában válassza ki a „Sample data model” elemet.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="b5c5a-174">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="b5c5a-175">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="b5c5a-176">A Név mezőbe írja be a „Minta formátum” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="b5c5a-177">Minta formátum</span><span class="sxs-lookup"><span data-stu-id="b5c5a-177">Sample format</span></span>  
5. <span data-ttu-id="b5c5a-178">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-178">Click Create configuration.</span></span>
6. <span data-ttu-id="b5c5a-179">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-179">Click Designer.</span></span>
7. <span data-ttu-id="b5c5a-180">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="b5c5a-181">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="b5c5a-182">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-182">Click OK.</span></span>
10. <span data-ttu-id="b5c5a-183">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="b5c5a-184">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="b5c5a-185">A fában válassza ki ezt: „model\Company”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="b5c5a-186">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-186">Click Bind.</span></span>
14. <span data-ttu-id="b5c5a-187">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-187">Click Save.</span></span>
15. <span data-ttu-id="b5c5a-188">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-188">Close the page.</span></span>
    * <span data-ttu-id="b5c5a-189">A létrehozott formátum piszkozatverziójának futtatása tesztelésre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="b5c5a-190">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-190">Click Run.</span></span>
    * <span data-ttu-id="b5c5a-191">A verzió gyorslapon kattintson a Futtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="b5c5a-192">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-192">Click OK.</span></span>
    * <span data-ttu-id="b5c5a-193">Tekintse át a kimenetet, amely tartalmazza annak a vállalatnak a nevét, amelybe az ezt a formátumkonfigurációt futtató felhasználó be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="b5c5a-194">A létrehozott modell-hozzárendelési konfigurációt ez a formátumkonfigurációra használja, mivel csak egy konfiguráció érhető el, amely tartalmazza a szükséges modell-hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-194">The created model-mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="b5c5a-195">Alternatív ER-modell leképezés konfigurációjának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b5c5a-195">Add alternative ER model-mapping configuration</span></span>
1. <span data-ttu-id="b5c5a-196">A fastruktúrában válassza ki a „Sample data model” elemet.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="b5c5a-197">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="b5c5a-198">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="b5c5a-199">A név mezőben írja be a „Mintaleképezés (másodlagos)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="b5c5a-200">Minta-hozzárendelés (másodlagos)</span><span class="sxs-lookup"><span data-stu-id="b5c5a-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="b5c5a-201">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-201">Click Create configuration.</span></span>
6. <span data-ttu-id="b5c5a-202">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-202">Click Designer.</span></span>
7. <span data-ttu-id="b5c5a-203">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-203">Click Designer.</span></span>
8. <span data-ttu-id="b5c5a-204">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="b5c5a-205">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-205">Click Add root.</span></span>
10. <span data-ttu-id="b5c5a-206">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="b5c5a-207">Cég</span><span class="sxs-lookup"><span data-stu-id="b5c5a-207">Company</span></span>  
11. <span data-ttu-id="b5c5a-208">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="b5c5a-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="b5c5a-209">CompanyInfo</span></span>  
12. <span data-ttu-id="b5c5a-210">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-210">Click OK.</span></span>
13. <span data-ttu-id="b5c5a-211">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-211">Click Edit.</span></span>
14. <span data-ttu-id="b5c5a-212">A fában válassza ki a 'String\CONCATENATE' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="b5c5a-213">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-213">Click Add function.</span></span>
16. <span data-ttu-id="b5c5a-214">A fastruktúrában bontsa ki ezt: „Company”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="b5c5a-215">A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="b5c5a-216">A fastruktúrában válassza ki ezt: „Company\find()\Name”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="b5c5a-217">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-217">Click Add data source.</span></span>
20. <span data-ttu-id="b5c5a-218">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="b5c5a-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="b5c5a-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="b5c5a-220">A fastruktúrában válassza ki ezt: „Company\find()\Company(DataArea)”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="b5c5a-221">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-221">Click Add data source.</span></span>
23. <span data-ttu-id="b5c5a-222">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="b5c5a-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="b5c5a-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="b5c5a-224">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-224">Click Save.</span></span>
25. <span data-ttu-id="b5c5a-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-225">Close the page.</span></span>
26. <span data-ttu-id="b5c5a-226">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-226">Click Save.</span></span>
27. <span data-ttu-id="b5c5a-227">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-227">Close the page.</span></span>
28. <span data-ttu-id="b5c5a-228">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-228">Close the page.</span></span>
29. <span data-ttu-id="b5c5a-229">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="b5c5a-230">Meglévő ER-modell leképezés konfiguráció használata</span><span class="sxs-lookup"><span data-stu-id="b5c5a-230">Use an existing ER model-mapping configuration</span></span>
1. <span data-ttu-id="b5c5a-231">A fában válassza a „Sample data model\Sample format” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="b5c5a-232">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-232">Click Run.</span></span>
    * <span data-ttu-id="b5c5a-233">Az ER-formátumkonfigurációhoz kijelölt piszkozatverzió nem hajtható végre, mert egynél több modell-hozzárendelési konfiguráció áll rendelkezésre a nem definiált adatmodellhez, amely a futó ER-formátum adatforrásaként van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-233">The selected draft version of the ER format configuration can't be executed because there is more than one model-mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="b5c5a-234">Ezt követően meg fogja adni, hogy a másodlagos modell-hozzárendelési konfiguráció legyen az, amelynek a modell-hozzárendelései lesznek használva a futó ER-formátum adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-234">Next, you will define the alternative model-mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="b5c5a-235">A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="b5c5a-236">Válassza az Igen lehetőséget a Modell-leképezés alapértelmezett értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-236">Select Yes in the Default for model-mapping field.</span></span>
5. <span data-ttu-id="b5c5a-237">A fában válassza a „Sample data model\Sample format” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="b5c5a-238">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-238">Click Run.</span></span>
7. <span data-ttu-id="b5c5a-239">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-239">Click OK.</span></span>
    * <span data-ttu-id="b5c5a-240">Ez a formátumkonfiguráció az alapértelmezett modell-hozzárendelési konfigurációt használja az elektronikus dokumentum létrehozásához (a létrehozott kimenet tartalmazza a vállalatkódot).</span><span class="sxs-lookup"><span data-stu-id="b5c5a-240">The default model-mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

