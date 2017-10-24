--- 
title: "Elektronikus jelentéskészítési (ER) konfiguráció feltöltése a Lifecycle Services rendszerbe"
description: "A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új Elektronikus jelentés (ER) konfigurációt és hogyan töltheti fel a Microsoft Lifecycle Services (LCS) rendszerbe."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.openlocfilehash: d24679a380ec824fe08c56aacb4bc348ff40440a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="c7da1-103">Elektronikus jelentéskészítési (ER) konfiguráció feltöltése a Lifecycle Services rendszerbe</span><span class="sxs-lookup"><span data-stu-id="c7da1-103">Upload a configuration into Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c7da1-104">A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új Elektronikus jelentés (ER) konfigurációt és hogyan töltheti fel a Microsoft Lifecycle Services (LCS) rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="c7da1-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="c7da1-105">Ebben a példában a mintavállalatra, a Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót, és feltölti az LCS rendszerbe. Ezeket a lépéseket a vállalatok között megosztott ER konfigurációkként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="c7da1-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="c7da1-106">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="c7da1-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="c7da1-107">Az LCS rendszerbe való hozzáféréshez végre kell hajtani ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c7da1-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="c7da1-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c7da1-109">Válassza ki a Litware, Inc. lehetőséget,</span><span class="sxs-lookup"><span data-stu-id="c7da1-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="c7da1-110">és állítsa be aktívként.</span><span class="sxs-lookup"><span data-stu-id="c7da1-110">and set it as active.</span></span>
3. <span data-ttu-id="c7da1-111">Kattintson a Konfigurációk lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="c7da1-112">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="c7da1-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="c7da1-113">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="c7da1-114">Egy olyan konfigurációt hoz létre, amely tartalmazza az elektronikus dokumentumokra vonatkozó minta adatmodellt.</span><span class="sxs-lookup"><span data-stu-id="c7da1-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="c7da1-115">Később az LCS-be töltik fel ezen adatmodell konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="c7da1-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="c7da1-116">A név mezőben írja be a „Minta modell beállítása” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c7da1-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="c7da1-117">Minta modell beállítása</span><span class="sxs-lookup"><span data-stu-id="c7da1-117">Sample model configuration</span></span>  
3. <span data-ttu-id="c7da1-118">A Leírás mezőben írja be a „Minta modell beállítása” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c7da1-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="c7da1-119">Minta modell beállítása</span><span class="sxs-lookup"><span data-stu-id="c7da1-119">Sample model configuration</span></span>  
4. <span data-ttu-id="c7da1-120">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-120">Click Create configuration.</span></span>
5. <span data-ttu-id="c7da1-121">Kattintson a Modelltervező lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-121">Click Model designer.</span></span>
6. <span data-ttu-id="c7da1-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-122">Click New.</span></span>
7. <span data-ttu-id="c7da1-123">A Név mezőbe írja be az „Belépési pont” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c7da1-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="c7da1-124">Belépési pont</span><span class="sxs-lookup"><span data-stu-id="c7da1-124">Entry point</span></span>  
8. <span data-ttu-id="c7da1-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-125">Click Add.</span></span>
9. <span data-ttu-id="c7da1-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-126">Click Save.</span></span>
10. <span data-ttu-id="c7da1-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-127">Close the page.</span></span>
11. <span data-ttu-id="c7da1-128">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-128">Click Change status.</span></span>
12. <span data-ttu-id="c7da1-129">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-129">Click Complete.</span></span>
13. <span data-ttu-id="c7da1-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="c7da1-131">Új tárház regisztrálása</span><span class="sxs-lookup"><span data-stu-id="c7da1-131">Register a new  repository</span></span>
1. <span data-ttu-id="c7da1-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-132">Close the page.</span></span>
2. <span data-ttu-id="c7da1-133">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-133">Click Repositories.</span></span>
    * <span data-ttu-id="c7da1-134">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="c7da1-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="c7da1-135">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c7da1-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="c7da1-136">Ez lehetővé teszi az új tárház hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="c7da1-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="c7da1-137">A Konfiguráció tárházának típusa mezőben válassza ki az LCS lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c7da1-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="c7da1-138">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-138">Click Create repository.</span></span>
6. <span data-ttu-id="c7da1-139">A Projekt mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c7da1-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="c7da1-140">Válassza ki a kívánt LCS projektet.</span><span class="sxs-lookup"><span data-stu-id="c7da1-140">Select the desired LCS project.</span></span> <span data-ttu-id="c7da1-141">Hozzáféréssel kell rendelkeznie a projekthez.</span><span class="sxs-lookup"><span data-stu-id="c7da1-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="c7da1-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-142">Click OK.</span></span>
    * <span data-ttu-id="c7da1-143">Fejezze be az új tárház bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="c7da1-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="c7da1-144">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c7da1-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c7da1-145">Válassza ki az LCS tárházrekordot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="c7da1-146">Vegye figyelembe, hogy azon jelenlegi szolgáltatói jelentés jelölte meg a regisztrált tárházat, amely a tárházban megadható szolgáltató konfigurációját képezik és ennek megfelelően vannak feltöltve a kiválasztott LCS projektbe.</span><span class="sxs-lookup"><span data-stu-id="c7da1-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="c7da1-147">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-147">Click Open.</span></span>
    * <span data-ttu-id="c7da1-148">Nyissa meg a tárházat az ER konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="c7da1-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="c7da1-149">Üres lesz, ha a projektet még nem használta az ER-konfigurációk megosztásához.</span><span class="sxs-lookup"><span data-stu-id="c7da1-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="c7da1-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-150">Close the page.</span></span>
11. <span data-ttu-id="c7da1-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="c7da1-152">Konfigurációs feltöltése az LCS rendszerbe</span><span class="sxs-lookup"><span data-stu-id="c7da1-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="c7da1-153">Kattintson a Konfigurációk lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-153">Click Configurations.</span></span>
2. <span data-ttu-id="c7da1-154">A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c7da1-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="c7da1-155">Válassza ki a létrehozott, és már befejezett konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="c7da1-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="c7da1-156">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c7da1-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c7da1-157">Válassza ki a „Befejezett” állapotú kijelölt konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="c7da1-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="c7da1-158">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-158">Click Change status.</span></span>
5. <span data-ttu-id="c7da1-159">Kattintson a Megosztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7da1-159">Click Share.</span></span>
    * <span data-ttu-id="c7da1-160">A konfiguráció állapota „Kész” állapotról „Megosztott” állapotra változik az LCS-ben történő közzétételkor.</span><span class="sxs-lookup"><span data-stu-id="c7da1-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="c7da1-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-161">Click OK.</span></span>
7. <span data-ttu-id="c7da1-162">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c7da1-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c7da1-163">Válassza ki a „Megosztott” állapotú konfiguráció verziót.</span><span class="sxs-lookup"><span data-stu-id="c7da1-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="c7da1-164">Vegye figyelembe, hogy a kiválasztott verzió állapota „Kész” állapotról „Megosztott” állapotra változott.</span><span class="sxs-lookup"><span data-stu-id="c7da1-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="c7da1-165">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7da1-165">Close the page.</span></span>
9. <span data-ttu-id="c7da1-166">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-166">Click Repositories.</span></span>
    * <span data-ttu-id="c7da1-167">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="c7da1-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="c7da1-168">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="c7da1-168">Click Open.</span></span>
    * <span data-ttu-id="c7da1-169">Válassza ki a LCS tárházat és nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="c7da1-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="c7da1-170">Vegye figyelembe, hogy a kijelölt konfiguráció a kiválasztott projekt LCS eszközeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c7da1-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="c7da1-171">Nyissa meg az LCS lehetőséget a https://lcs.dynamics.com honlap segítségével. Nyissa meg a korábban a tárház regisztrálásához használt projektet, majd nyissa meg a projekt „Eszköztár” lehetőségét, és bontsa ki a „GER konfiguráció” eszköztár tartalmát - Elérhető lesz a feltöltött ER-konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="c7da1-171">Open LCS using https://lcs.dynamics.com. Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="c7da1-172">Vegye figyelembe, hogy a feltöltött LCS konfigurációt egy másik Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás példányába importálhatja, ha a szolgáltatók rendelkeznek hozzáféréssel ehhez az LCS projekthez.</span><span class="sxs-lookup"><span data-stu-id="c7da1-172">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations, Enterprise edition instance if providers have access to this LCS project.</span></span>  

