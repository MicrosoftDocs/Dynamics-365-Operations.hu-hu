---
title: Új projekt létrehozása
description: Ez a témakör új projekt létrehozásával kapcsolatban tartalmaz tájékoztatást.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760563"
---
# <a name="create-a-new-project"></a><span data-ttu-id="29c80-103">Új projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="29c80-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29c80-104">Új projekt létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="29c80-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="29c80-105">A **Projektvezetés** oldalon válassza az **Új projekt** lehetőséget, és adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="29c80-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="29c80-106">**Projekt típusa:** Idő és anyag</span><span class="sxs-lookup"><span data-stu-id="29c80-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="29c80-107">**Projekt neve:** XYZ Frissítési Fázis 2</span><span class="sxs-lookup"><span data-stu-id="29c80-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="29c80-108">**Projektcsoport:** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="29c80-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="29c80-109">**Projektszerződés azonosítója:** 00000002</span><span class="sxs-lookup"><span data-stu-id="29c80-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="29c80-110">Válassza a **Projekt létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="29c80-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="29c80-111">Erőforrás hozzárendelése egy projekthez</span><span class="sxs-lookup"><span data-stu-id="29c80-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="29c80-112">A **Dolgozók** oldalon a **Dolgozók** listában válassza ki az ahhoz a dolgozóhoz tartozó rekordot, akihez korábban kompetenciákat állított be, majd nyissa meg azt.</span><span class="sxs-lookup"><span data-stu-id="29c80-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="29c80-113">A Műveleti ablaktáblán a **Projekt** lapon a **Beállítás** csoportban válassza a **Projekt hozzárendelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="29c80-114">Az **Erőforrás-ellenőrzés projekt-hozzárendelései** oldalon a **Projektek** lapon a **Projekt hozzáadása a kiválasztott projektekhez** mezőben alkalmazzon szűrőt az **XYZ frissítési szakasz 2** projektre.</span><span class="sxs-lookup"><span data-stu-id="29c80-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="29c80-115">A **Fennmaradó projektek** ablaktáblán válasszon ki egy projektet, majd válassza a nyílgombot, hogy hozzáadja azt a **Kiválasztott projektek** ablaktáblához.</span><span class="sxs-lookup"><span data-stu-id="29c80-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="29c80-116">Igény szerint hozzárendelhet kategóriákat egy erőforráshoz.</span><span class="sxs-lookup"><span data-stu-id="29c80-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="29c80-117">A kategória típusa **Költség** vagy **Bevétel** lehet.</span><span class="sxs-lookup"><span data-stu-id="29c80-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="29c80-118">A kategória típusát a szervezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="29c80-118">The category type is determined by your organization.</span></span> <span data-ttu-id="29c80-119">Ha nincsenek az erőforráshoz hozzárendelt kategóriák, a Finance kikeresi az alapértelmezett óránkénti árat a költségekhez és bevételekhez.</span><span class="sxs-lookup"><span data-stu-id="29c80-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="29c80-120">Projekt erőforrások és szerepkör jellemzők beállítása</span><span class="sxs-lookup"><span data-stu-id="29c80-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="29c80-121">A projektvezető a projekterőforrás funkció segítségével hozhat létre a projekthez szükséges szerepköröket.</span><span class="sxs-lookup"><span data-stu-id="29c80-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="29c80-122">A szerepkörök akkor használhatóak, ha a visszaigazolt erőforrások ismeretlenek az erőforrások fenntartásakor.</span><span class="sxs-lookup"><span data-stu-id="29c80-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="29c80-123">A szerepkörök ideiglenes fenntarthatók tervezett erőforrásként, így tovább folytathatja a projekttervezést.</span><span class="sxs-lookup"><span data-stu-id="29c80-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="29c80-124">[![Példa szerepkörre](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="29c80-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="29c80-125">**Forgatókönyv:** Contoso egy olyan Idő- és anyagprojekt elvégzésére lett felvéve, amely rendelkezik egy jóváhagyott projekt alapszabállyal.</span><span class="sxs-lookup"><span data-stu-id="29c80-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="29c80-126">A beosztott projektvezető továbbra is a projekt hatókörét tölti ki.</span><span class="sxs-lookup"><span data-stu-id="29c80-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="29c80-127">Az erőforrás-kezelő jelenleg azokat a fenntartott erőforrásokat azonosítja, amelyek az új projekthez lesznek rendelve.</span><span class="sxs-lookup"><span data-stu-id="29c80-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="29c80-128">A projekt kritikus jellege miatt a projekttámogató a Vezető projektmenedzser szerepkört kérte.</span><span class="sxs-lookup"><span data-stu-id="29c80-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="29c80-129">Az erőforrás-kezelőnek új erőforrást kell szereznie, majd meghatároznia a szerepkört a rendszerben, hogy ha a beosztott projektvezetőnek szüksége lenne az erőforrás-információkra a projekttervezés alatt, akkor az rendelkezésre álljon.</span><span class="sxs-lookup"><span data-stu-id="29c80-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="29c80-130">Az alábbi lépések bemutatják, hogy az erőforrás-kezelő hogyan tud beállítani Vezető projektmenedzser szerepkört a rendszerben, valamint hogyan tud erőforrás jellemzőket társítani hozzá.</span><span class="sxs-lookup"><span data-stu-id="29c80-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="29c80-131">A későbbiek folyamán a szerepkör használható lesz olyan kereséseknél, amelyek azon elérhető erőforrásokat keresik meg, amelyek megfelelnek a szükséges erőforrás kompetenciáknak.</span><span class="sxs-lookup"><span data-stu-id="29c80-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="29c80-132">A **Szerepkörök beállítása** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="29c80-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="29c80-133">**Szerepkör-azonosító:** Vezető Projektmenedzser</span><span class="sxs-lookup"><span data-stu-id="29c80-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="29c80-134">**Leírás:** Vezető Projektmenedzser</span><span class="sxs-lookup"><span data-stu-id="29c80-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="29c80-135">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-135">Select **Create**.</span></span>
3. <span data-ttu-id="29c80-136">Válassza a **Vezető projektmenedzser** szerepkört, és válassza a **Jellemzők konfigurálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="29c80-137">A **Jellemzők típusa** mezőben válassza ki a **Szakértelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="29c80-138">Az **Elérhető jellemzők** mezőbe írja be a keresett szakértelem típusát.</span><span class="sxs-lookup"><span data-stu-id="29c80-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="29c80-139">A **Jellemző típusa** mezőben válassza ki a **Diploma** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="29c80-140">Az **Elérhető jellemzők** mezőbe írja be a keresett diploma típusát.</span><span class="sxs-lookup"><span data-stu-id="29c80-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="29c80-141">Projekterőforrás hozzárendelése egy projekthez</span><span class="sxs-lookup"><span data-stu-id="29c80-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="29c80-142">A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.</span><span class="sxs-lookup"><span data-stu-id="29c80-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="29c80-143">A **Projektcsapat és ütemezés** fülön válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="29c80-144">A **Szerepkör** mezőben válassza a **Csapat tagja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="29c80-145">Válassza a **Foglalás naptárból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="29c80-146">Az **Erőforrás elérhetősége** lapon válassza a **Beállítások megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="29c80-147">A **Nézet beállításának módosítása** lapon adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="29c80-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="29c80-148">**Dátumtartomány-nézet formátuma:** Nap</span><span class="sxs-lookup"><span data-stu-id="29c80-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="29c80-149">**Elérhetőség leírásának megjelenítése:** Igen</span><span class="sxs-lookup"><span data-stu-id="29c80-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="29c80-150">**Hátralévő kapacitás megjelenítése:** Igen</span><span class="sxs-lookup"><span data-stu-id="29c80-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="29c80-151">Az erőforrások listájából válasszon egy erőforrást.</span><span class="sxs-lookup"><span data-stu-id="29c80-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="29c80-152">Válassza a **Végleges lefoglalás** és a **Teljes kapacitás** lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="29c80-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="29c80-153">Erőforrás hozzárendelése egy alapértelmezett szerepkörhöz</span><span class="sxs-lookup"><span data-stu-id="29c80-153">Assign a resource to a default role</span></span>

<span data-ttu-id="29c80-154">A projekthez fenntartható erőforrásokon történő leásás segítheti a projektvezetőket és az erőforrás-kezelőket.</span><span class="sxs-lookup"><span data-stu-id="29c80-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="29c80-155">Alapértelmezett szerepkört társíthat már meglévő, valamint újonnan szerzett erőforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="29c80-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="29c80-156">Amikor például Danielt felvették, megfelelő tapasztalattal és készségekkel rendelkezett az üzleti elemző szerep betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="29c80-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="29c80-157">Az erőforrás-kezelő ezt a szerepkört rendelte Danielhez alapértelmezett szerepkörként.</span><span class="sxs-lookup"><span data-stu-id="29c80-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="29c80-158">Ezért az erőforrás-kezelő Danielt hozzáadta az üzleti elemzők készletéhez, akik rendelkezésre állnak a projekteken végzett munkához.</span><span class="sxs-lookup"><span data-stu-id="29c80-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="29c80-159">Erőforrás-fenntartás során a projektvezetők szűrhetik a szerepkör erőforrásait, amelyek rendelkezésre állnak projekteken való munkához.</span><span class="sxs-lookup"><span data-stu-id="29c80-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="29c80-160">Ezeket az adatokat használhatják egy feltételként több kritérium felhasználásával történő döntéshozatal végrehajtásakor erőforrás teljesítése során.</span><span class="sxs-lookup"><span data-stu-id="29c80-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="29c80-161">Más erőforrás tulajdonságait is hozzáadhatják a szűrőhöz meghatározott szakértelemmel, végzettséggel és adott projekttapasztalattal rendelkező erőforrások keresésekor.</span><span class="sxs-lookup"><span data-stu-id="29c80-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="29c80-162">**Eset:** Egy jóváhagyott projekt elindult, és a Vezető projektmenedzser szerepkört tervezett erőforrásként tartották fenn a projekt tervezési szakaszában.</span><span class="sxs-lookup"><span data-stu-id="29c80-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="29c80-163">Az erőforrás-kezelő már megszerezte az erőforrást a Vezető projektmenedzser szerepkör betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="29c80-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="29c80-164">Az **Erőforráslista** oldalon válassza a **Daniel Goldschmidt** nevet.</span><span class="sxs-lookup"><span data-stu-id="29c80-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="29c80-165">Az **Erőforrás szerepköre** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="29c80-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="29c80-166">**Hatályos:** adja meg a jelenlegi dátumot.</span><span class="sxs-lookup"><span data-stu-id="29c80-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="29c80-167">**Lejárat:** adja meg a **Soha** értéket.</span><span class="sxs-lookup"><span data-stu-id="29c80-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="29c80-168">**Szerepkör:** adja meg a **Vezető Projektmenedzser** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29c80-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="29c80-169">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="29c80-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="29c80-170">A **Kompetenciák** lapon adja hozzá a **ProjectMgmt** szakértelem és **PMP** tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="29c80-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
