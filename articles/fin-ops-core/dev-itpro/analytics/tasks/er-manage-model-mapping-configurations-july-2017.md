---
title: ER modell-leképezés kezelése külön ER-konfigurációkban
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).
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
ms.openlocfilehash: 4e59e9f2dd5a0fa6d5955e3d93d25759a478ede7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684427"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="90e9c-103">ER modell-leképezés kezelése külön ER-konfigurációkban</span><span class="sxs-lookup"><span data-stu-id="90e9c-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90e9c-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="90e9c-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="90e9c-105">Ebben a feladat-útmutatóban létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő feladat-útmutató lépéseit kell végrehajtani: „ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, "ER Create a configuration provider" and mark it as active.</span></span> 

<span data-ttu-id="90e9c-106">Mivel az ER-konfigurációk meg vannak osztva a vállalatok között, a feladat-útmutatót a tetszése szerint vállalat-adatkészlettel hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="90e9c-107">A Feladat útmutató a funkcionalitása akkor érhető el, ha telepítette a következő gyorsjavítások valamelyikét: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 a Dynamics AX 7.0-s verzióhoz vagy https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 a Dynamics 365 for Operations verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="90e9c-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="90e9c-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="90e9c-109">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="90e9c-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="90e9c-110">Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” feladat-útmutatóban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="90e9c-110">If you don't see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider, and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="90e9c-111">Új ER-modellkonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="90e9c-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="90e9c-112">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="90e9c-113">Új modellkonfiguráció hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="90e9c-113">Add a new model configuration.</span></span> <span data-ttu-id="90e9c-114">A névnek egyedinek kell lennie a konfigurációfában.</span><span class="sxs-lookup"><span data-stu-id="90e9c-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="90e9c-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="90e9c-116">A Név mezőben írja be a „Minta adatmodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="90e9c-117">Minta adatmodell</span><span class="sxs-lookup"><span data-stu-id="90e9c-117">Sample data model</span></span>  
4. <span data-ttu-id="90e9c-118">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-118">Click Create configuration.</span></span>
5. <span data-ttu-id="90e9c-119">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-119">Click Designer.</span></span>
6. <span data-ttu-id="90e9c-120">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="90e9c-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="90e9c-121">A Név mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="90e9c-122">Gyökér</span><span class="sxs-lookup"><span data-stu-id="90e9c-122">Root</span></span>  
8. <span data-ttu-id="90e9c-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-123">Click Add.</span></span>
9. <span data-ttu-id="90e9c-124">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="90e9c-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="90e9c-125">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="90e9c-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="90e9c-126">Cég</span><span class="sxs-lookup"><span data-stu-id="90e9c-126">Company</span></span>  
11. <span data-ttu-id="90e9c-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-127">Click Add.</span></span>
12. <span data-ttu-id="90e9c-128">A Leírás mezőben adja meg 'A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben' szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="90e9c-129">A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben.</span><span class="sxs-lookup"><span data-stu-id="90e9c-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="90e9c-130">Kattintson a Gyökérhivatkozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-130">Click Root reference.</span></span>
14. <span data-ttu-id="90e9c-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-131">Click OK.</span></span>
15. <span data-ttu-id="90e9c-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-132">Click Save.</span></span>
16. <span data-ttu-id="90e9c-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-133">Close the page.</span></span>
17. <span data-ttu-id="90e9c-134">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-134">Click Change status.</span></span>
18. <span data-ttu-id="90e9c-135">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-135">Click Complete.</span></span>
19. <span data-ttu-id="90e9c-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="90e9c-137">Új ER-modellhozzárendeléskonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="90e9c-137">Add a new ER model-mapping configuration</span></span>
1. <span data-ttu-id="90e9c-138">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="90e9c-139">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="90e9c-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="90e9c-140">A Név mezőbe írja be a „Minta hozzárendelés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="90e9c-141">Minta leképezés</span><span class="sxs-lookup"><span data-stu-id="90e9c-141">Sample mapping</span></span>  
4. <span data-ttu-id="90e9c-142">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-142">Click Create configuration.</span></span>
5. <span data-ttu-id="90e9c-143">Bontsa ki az Előfeltételek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="90e9c-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="90e9c-144">Az Implementációk előfeltételcsoport automatikusan hozzá van adva.</span><span class="sxs-lookup"><span data-stu-id="90e9c-144">The Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="90e9c-145">A csoport tartalmazza a szülő adatmodell-konfigurációra hivatkozó előfeltétel-ellenőrzési összetevőt, és Implementációként van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="90e9c-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="90e9c-146">Ez azt jelenti, hogy ez a Mintahozzárendelés modellhozzárendelési konfiguráció a Minta adatmodell implementációjának minősül.</span><span class="sxs-lookup"><span data-stu-id="90e9c-146">This means that this Sample-mapping model-mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="90e9c-147">Ezért ez az összetevő arra kényszeríti az ER-t, hogy mindig letöltse egy ER-tárházból a Minta-hozzárendelés modell-hozzárendelési konfigurációt, amikor letölti a Minta adatmodell modellkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="90e9c-147">Therefore, this component will force ER to download the model-mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="90e9c-148">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-148">Click Designer.</span></span>
    * <span data-ttu-id="90e9c-149">A létrehozott modell-hozzárendelési konfiguráció egy új, üres hozzárendelést tartalmaz, amelynek a neve azonos a létrehozott konfiguráció nevével.</span><span class="sxs-lookup"><span data-stu-id="90e9c-149">The created model-mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="90e9c-150">Ha egy kijelölt szülő modellkonfiguráció modell-hozzárendeléseket tartalmaz, ha azok át lesznek másolva egy új modell-hozzárendelési konfigurációba.</span><span class="sxs-lookup"><span data-stu-id="90e9c-150">When a selected parent model configuration contains model mappings, they will be copied to a new model-mapping configuration.</span></span>   
7. <span data-ttu-id="90e9c-151">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-151">Click Designer.</span></span>
8. <span data-ttu-id="90e9c-152">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.</span><span class="sxs-lookup"><span data-stu-id="90e9c-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="90e9c-153">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-153">Click Add root.</span></span>
10. <span data-ttu-id="90e9c-154">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="90e9c-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="90e9c-155">Cég</span><span class="sxs-lookup"><span data-stu-id="90e9c-155">Company</span></span>  
11. <span data-ttu-id="90e9c-156">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="90e9c-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="90e9c-157">CompanyInfo</span></span>  
12. <span data-ttu-id="90e9c-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-158">Click OK.</span></span>
13. <span data-ttu-id="90e9c-159">A fastruktúrában bontsa ki ezt: „Company”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="90e9c-160">A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.</span><span class="sxs-lookup"><span data-stu-id="90e9c-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="90e9c-161">A fastruktúrában válassza ki ezt: „Company\find()\Name”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="90e9c-162">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-162">Click Bind.</span></span>
17. <span data-ttu-id="90e9c-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-163">Click Save.</span></span>
18. <span data-ttu-id="90e9c-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-164">Close the page.</span></span>
19. <span data-ttu-id="90e9c-165">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-165">Close the page.</span></span>
20. <span data-ttu-id="90e9c-166">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="90e9c-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="90e9c-167">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-167">Click User parameters.</span></span>
22. <span data-ttu-id="90e9c-168">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="90e9c-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="90e9c-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-169">Click OK.</span></span>
24. <span data-ttu-id="90e9c-170">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-170">Click Edit.</span></span>
25. <span data-ttu-id="90e9c-171">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="90e9c-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="90e9c-172">Új ER-formátum hozzáadása</span><span class="sxs-lookup"><span data-stu-id="90e9c-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="90e9c-173">A fastruktúrában válassza ki a „Sample data model” elemet.</span><span class="sxs-lookup"><span data-stu-id="90e9c-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="90e9c-174">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="90e9c-175">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="90e9c-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="90e9c-176">A Név mezőbe írja be a „Minta formátum” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="90e9c-177">Minta formátum</span><span class="sxs-lookup"><span data-stu-id="90e9c-177">Sample format</span></span>  
5. <span data-ttu-id="90e9c-178">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-178">Click Create configuration.</span></span>
6. <span data-ttu-id="90e9c-179">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-179">Click Designer.</span></span>
7. <span data-ttu-id="90e9c-180">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="90e9c-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="90e9c-181">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="90e9c-182">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-182">Click OK.</span></span>
10. <span data-ttu-id="90e9c-183">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="90e9c-184">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="90e9c-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="90e9c-185">A fában válassza ki ezt: „model\Company”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="90e9c-186">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-186">Click Bind.</span></span>
14. <span data-ttu-id="90e9c-187">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-187">Click Save.</span></span>
15. <span data-ttu-id="90e9c-188">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-188">Close the page.</span></span>
    * <span data-ttu-id="90e9c-189">A létrehozott formátum piszkozatverziójának futtatása tesztelésre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="90e9c-190">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-190">Click Run.</span></span>
    * <span data-ttu-id="90e9c-191">A verzió gyorslapon kattintson a Futtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="90e9c-192">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-192">Click OK.</span></span>
    * <span data-ttu-id="90e9c-193">Tekintse át a kimenetet, amely tartalmazza annak a vállalatnak a nevét, amelybe az ezt a formátumkonfigurációt futtató felhasználó be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="90e9c-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="90e9c-194">A létrehozott modell-hozzárendelési konfigurációt ez a formátumkonfigurációra használja, mivel csak egy konfiguráció érhető el, amely tartalmazza a szükséges modell-hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="90e9c-194">The created model-mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="90e9c-195">Alternatív ER-modell leképezés konfigurációjának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="90e9c-195">Add alternative ER model-mapping configuration</span></span>
1. <span data-ttu-id="90e9c-196">A fastruktúrában válassza ki a „Sample data model” elemet.</span><span class="sxs-lookup"><span data-stu-id="90e9c-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="90e9c-197">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="90e9c-198">Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="90e9c-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="90e9c-199">A név mezőben írja be a „Mintaleképezés (másodlagos)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="90e9c-200">Minta-hozzárendelés (másodlagos)</span><span class="sxs-lookup"><span data-stu-id="90e9c-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="90e9c-201">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-201">Click Create configuration.</span></span>
6. <span data-ttu-id="90e9c-202">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-202">Click Designer.</span></span>
7. <span data-ttu-id="90e9c-203">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-203">Click Designer.</span></span>
8. <span data-ttu-id="90e9c-204">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.</span><span class="sxs-lookup"><span data-stu-id="90e9c-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="90e9c-205">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-205">Click Add root.</span></span>
10. <span data-ttu-id="90e9c-206">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="90e9c-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="90e9c-207">Cég</span><span class="sxs-lookup"><span data-stu-id="90e9c-207">Company</span></span>  
11. <span data-ttu-id="90e9c-208">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="90e9c-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="90e9c-209">CompanyInfo</span></span>  
12. <span data-ttu-id="90e9c-210">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-210">Click OK.</span></span>
13. <span data-ttu-id="90e9c-211">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90e9c-211">Click Edit.</span></span>
14. <span data-ttu-id="90e9c-212">A fában válassza ki a 'String\CONCATENATE' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="90e9c-213">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-213">Click Add function.</span></span>
16. <span data-ttu-id="90e9c-214">A fastruktúrában bontsa ki ezt: „Company”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="90e9c-215">A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.</span><span class="sxs-lookup"><span data-stu-id="90e9c-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="90e9c-216">A fastruktúrában válassza ki ezt: „Company\find()\Name”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="90e9c-217">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-217">Click Add data source.</span></span>
20. <span data-ttu-id="90e9c-218">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="90e9c-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="90e9c-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="90e9c-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="90e9c-220">A fastruktúrában válassza ki ezt: „Company\find()\Company(DataArea)”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="90e9c-221">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-221">Click Add data source.</span></span>
23. <span data-ttu-id="90e9c-222">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="90e9c-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="90e9c-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="90e9c-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="90e9c-224">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-224">Click Save.</span></span>
25. <span data-ttu-id="90e9c-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-225">Close the page.</span></span>
26. <span data-ttu-id="90e9c-226">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-226">Click Save.</span></span>
27. <span data-ttu-id="90e9c-227">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-227">Close the page.</span></span>
28. <span data-ttu-id="90e9c-228">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="90e9c-228">Close the page.</span></span>
29. <span data-ttu-id="90e9c-229">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="90e9c-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="90e9c-230">Meglévő ER-modell leképezés konfiguráció használata</span><span class="sxs-lookup"><span data-stu-id="90e9c-230">Use an existing ER model-mapping configuration</span></span>
1. <span data-ttu-id="90e9c-231">A fában válassza a „Sample data model\Sample format” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="90e9c-232">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-232">Click Run.</span></span>
    * <span data-ttu-id="90e9c-233">Az ER-formátumkonfigurációhoz kijelölt piszkozatverzió nem hajtható végre, mert egynél több modell-hozzárendelési konfiguráció áll rendelkezésre a nem definiált adatmodellhez, amely a futó ER-formátum adatforrásaként van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="90e9c-233">The selected draft version of the ER format configuration can't be executed because there is more than one model-mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="90e9c-234">Ezt követően meg fogja adni, hogy a másodlagos modell-hozzárendelési konfiguráció legyen az, amelynek a modell-hozzárendelései lesznek használva a futó ER-formátum adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="90e9c-234">Next, you will define the alternative model-mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="90e9c-235">A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.</span><span class="sxs-lookup"><span data-stu-id="90e9c-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="90e9c-236">Válassza az Igen lehetőséget a Modell-leképezés alapértelmezett értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="90e9c-236">Select Yes in the Default for model-mapping field.</span></span>
5. <span data-ttu-id="90e9c-237">A fában válassza a „Sample data model\Sample format” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90e9c-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="90e9c-238">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-238">Click Run.</span></span>
7. <span data-ttu-id="90e9c-239">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="90e9c-239">Click OK.</span></span>
    * <span data-ttu-id="90e9c-240">Ez a formátumkonfiguráció az alapértelmezett modell-hozzárendelési konfigurációt használja az elektronikus dokumentum létrehozásához (a létrehozott kimenet tartalmazza a vállalatkódot).</span><span class="sxs-lookup"><span data-stu-id="90e9c-240">The default model-mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

