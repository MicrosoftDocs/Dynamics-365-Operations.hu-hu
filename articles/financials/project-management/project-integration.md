---
title: "Microsoft Project-ügyfélintegráció"
description: "A projektek ütemtervének megtervezése és karbantartása összetett lehet, ezért a projektmenedzsereknek olyan eszközöket kell használniuk, amelyek segítenek nekik elvégezni ezt a feladatot. A Microsoft Project ügyféllel való integráció támogatást nyújt a projekt munkalebontási struktúrájának megnyitásához és kezeléséhez."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a3445417d5ae88e2ff3676962a82921a7ab475d
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="microsoft-project-client-integration"></a><span data-ttu-id="bc3df-104">Microsoft Project-ügyfélintegráció</span><span class="sxs-lookup"><span data-stu-id="bc3df-104">Microsoft Project client integration</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bc3df-105">A projektek ütemtervének megtervezése és karbantartása összetett lehet, ezért a projektmenedzsereknek olyan eszközöket kell használniuk, amelyek segítenek nekik elvégezni ezt a feladatot.</span><span class="sxs-lookup"><span data-stu-id="bc3df-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="bc3df-106">A Microsoft Project ügyféllel való integráció támogatást nyújt a projekt munkalebontási struktúrájának megnyitásához és kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="bc3df-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="bc3df-107">A projektmenedzser bármikor közzéteheti a változtatásokat a Finance and Operations projekt munkalebontási struktúrájába.</span><span class="sxs-lookup"><span data-stu-id="bc3df-107">The project manager can publish any changes back to the Finance and Operations project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="bc3df-108">Amennyiben a Microsoft Dynamics 365 for Finance and Operations 2017. júliusi frissítését használja, telepítenie kell a KB 4054797-et és 4055884-et.</span><span class="sxs-lookup"><span data-stu-id="bc3df-108">If you are using Microsoft Dynamics 365 for Finance and Operations, July update, you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="bc3df-109">A Microsoft Project ügyfél bővítmény konfigurálása</span><span class="sxs-lookup"><span data-stu-id="bc3df-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="bc3df-110">A Microsoft Project ügyféllel való integráció engedélyezéséhez a Microsoft Dynamics 365 ügyfelet telepíteni kell a felhasználó ügyfél Microsoft Project alkalmazásában.</span><span class="sxs-lookup"><span data-stu-id="bc3df-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="bc3df-111">Ehhez meg kel nyitni a **Projektvezetési munkaterületet**.</span><span class="sxs-lookup"><span data-stu-id="bc3df-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="bc3df-112">•   Kattintson az **Ügyfélbővítmény konfigurálása** elemre a munkaterület **Hivatkozások** > **Beállítás** részében.</span><span class="sxs-lookup"><span data-stu-id="bc3df-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="bc3df-113">• Kattintson a **Megnyitás** elemre, majd a kérdésnél kattintson az **Futtatás** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc3df-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="bc3df-114">Meglévő vázlat munkalebontási struktúra megnyitása és szerkesztése a Microsoft Project ügyfélben</span><span class="sxs-lookup"><span data-stu-id="bc3df-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="bc3df-115">Ha a projekt a Finance and Operations programban már rendelkezik létrehozott munkalebontási struktúrával, a munkalebontási struktúra megnyitható a Microsoft Project ügyfél alkalmazásban, ha a munkalebontási struktúra „vázlat” állapotú.</span><span class="sxs-lookup"><span data-stu-id="bc3df-115">If a project in Finance and Operations already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="bc3df-116">A **Projekt** oldalról történő megnyitáshoz kattintson a **Megnyitás a Microsoft Project programban** hivatkozásra a **Terv** lapon. Ez a lap a Microsoft Project ügyfél alkalmazáson belül is megnyitható a **Megnyitás** elemre kattintva a **Microsoft Dynamics 365** fülön. Válassza a **Jogi személy** és a **Projekt** lehetőséget a listából.</span><span class="sxs-lookup"><span data-stu-id="bc3df-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="bc3df-117">Ha Internet Explorer böngészőt használ, kattintson a **Mentés** elemre a fájl letöltési helyéről való manuális megnyitáshoz.</span><span class="sxs-lookup"><span data-stu-id="bc3df-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="bc3df-118">Másik lehetőségként kattintson **Mentés és megnyitás** elemre a fájlt a Microsoft Project ügyfélben történő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bc3df-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="bc3df-119">A mentés során ne nevezze át a fájlnevet.</span><span class="sxs-lookup"><span data-stu-id="bc3df-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="bc3df-120">Mielőtt bármilyen módosítást végezne a fájlban a Microsoft Project ügyfél használatával, ki kell vennie. Kattintson a **Kivétel** elemre a **Microsoft Dynamics 365** lapon. Ez megakadályozza, hogy más felhasználók egy időben szerkesszék a munkalebontási struktúrát a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="bc3df-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance and Operations at the same time.</span></span> <span data-ttu-id="bc3df-121">Ha szeretné közzétenni a munkalebontási struktúrát bármilyen módosítás befejezése után, kattintson a **Beadás** elemre a **Microsoft Dynamics 365** lapon.</span><span class="sxs-lookup"><span data-stu-id="bc3df-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="bc3df-122">Ha egy projektcsapat már hozzá lett adva a projekthez a Finance and Operations programban, a rendszer kitölti az erőforráslistát a csapattagokkal.</span><span class="sxs-lookup"><span data-stu-id="bc3df-122">If a project team has already been added to the project in Finance and Operations, the resource list will be populated with the team members.</span></span> <span data-ttu-id="bc3df-123">Ha projektcsapat még nincs hozzáadva a projekthez, kiválaszthat erőforrásokat kijelölése és létrehozhatja a csapatot a Microsoft Project ügyfélen belül, ha az **Erőforrások** gombra kattint a **Microsoft Dynamics 365** lapon.</span><span class="sxs-lookup"><span data-stu-id="bc3df-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="bc3df-124">A következő adatokat a rendszer visszafelé szinkronizálja a Finance and Operations irányába a beadási folyamat részeként:</span><span class="sxs-lookup"><span data-stu-id="bc3df-124">The following data will be synced back to Finance and Operations as part of the check in process:</span></span>

<span data-ttu-id="bc3df-125">•   Feladat neve</span><span class="sxs-lookup"><span data-stu-id="bc3df-125">•   Task name</span></span>

<span data-ttu-id="bc3df-126">•   Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="bc3df-126">•   Start date</span></span>

<span data-ttu-id="bc3df-127">•   Befejezési dátum</span><span class="sxs-lookup"><span data-stu-id="bc3df-127">•   Finish date</span></span>

<span data-ttu-id="bc3df-128">•   Megelőző tevékenységek</span><span class="sxs-lookup"><span data-stu-id="bc3df-128">•   Predecessors</span></span>

<span data-ttu-id="bc3df-129">•   Erőforrásnevek</span><span class="sxs-lookup"><span data-stu-id="bc3df-129">•   Resource names</span></span>

<span data-ttu-id="bc3df-130">•   Kategória</span><span class="sxs-lookup"><span data-stu-id="bc3df-130">•   Category</span></span>

<span data-ttu-id="bc3df-131">•   Erőforrás-kategória</span><span class="sxs-lookup"><span data-stu-id="bc3df-131">•   Resource category</span></span>

<span data-ttu-id="bc3df-132">•   Munkaórák</span><span class="sxs-lookup"><span data-stu-id="bc3df-132">•   Work hours</span></span>

<span data-ttu-id="bc3df-133">•   Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc3df-133">•   Notes</span></span>

<span data-ttu-id="bc3df-134">•   Prioritás</span><span class="sxs-lookup"><span data-stu-id="bc3df-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="bc3df-135">Ha más oszlopokat ad hozzá a Microsoft Project ügyfél fájlhoz, akkor ezek nem lesznek elmentve a fájlba, és nem jelennek meg a fájl megnyitásakor.</span><span class="sxs-lookup"><span data-stu-id="bc3df-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="bc3df-136">Meglévő projekt munkalebontási struktúrájának létrehozása a Microsoft Project ügyfél segítségével</span><span class="sxs-lookup"><span data-stu-id="bc3df-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="bc3df-137">Új munkalebontási struktúra létrehozásához a Microsoft Project ügyfél segítségével kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bc3df-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="bc3df-138">Nyissa meg a Microsoft Project ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="bc3df-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="bc3df-139">A **Microsoft Dynamics 365** lapon kattintson a **megnyitás** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc3df-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="bc3df-140">Válassza **Jogi személyt** a projekthez.</span><span class="sxs-lookup"><span data-stu-id="bc3df-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="bc3df-141">Válassza ki a kívánt **Projektet**.</span><span class="sxs-lookup"><span data-stu-id="bc3df-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="bc3df-142">A **Microsoft Dynamics 365** lapon kattintson a **Kivétel** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc3df-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="bc3df-143">Ha készen áll a Finance and Operations programba történő közzétételre, kattintson a **Beadás** elemre a **Microsoft Dynamics 365** lapon.</span><span class="sxs-lookup"><span data-stu-id="bc3df-143">When ready to publish to Finance and Operations, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="bc3df-144">Meglévő projekt meglévő munkalebontási struktúrájának cseréje a Microsoft Project ügyfél segítségével</span><span class="sxs-lookup"><span data-stu-id="bc3df-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="bc3df-145">A Microsoft Project ügyfél segítségével új munkalebontási struktúra létrehozásához és egy meglévő projekt meglévő munkalebontási struktúra lecseréléséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bc3df-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="bc3df-146">Nyissa meg a Microsoft Project ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="bc3df-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="bc3df-147">Hozza létre az ütemezést a Microsoft Project ügyfélben.</span><span class="sxs-lookup"><span data-stu-id="bc3df-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="bc3df-148">A **Microsoft Dynamics 365** lapon kattintson a **Módosítások mentése** > **Meglévő projekt lecserélése** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc3df-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="bc3df-149">Válassza **Jogi személyt** a projekthez.</span><span class="sxs-lookup"><span data-stu-id="bc3df-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="bc3df-150">Válassza ki a kívánt **Projektet**.</span><span class="sxs-lookup"><span data-stu-id="bc3df-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="bc3df-151">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bc3df-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="bc3df-152">Új projekt létrehozása a Microsoft Project ügyfélen belül</span><span class="sxs-lookup"><span data-stu-id="bc3df-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="bc3df-153">Nyissa meg a Microsoft Project ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="bc3df-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="bc3df-154">Hozza létre az ütemezést a Microsoft Project ügyfélben.</span><span class="sxs-lookup"><span data-stu-id="bc3df-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="bc3df-155">A **Microsoft Dynamics 365** lapon kattintson a **Módosítások mentése** > **Mentés új projektbe** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc3df-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="bc3df-156">Válassza **Jogi személyt** a projekthez.</span><span class="sxs-lookup"><span data-stu-id="bc3df-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="bc3df-157">Adja meg a **Projektazonosító** értékét, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="bc3df-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="bc3df-158">Írja be a **Projekt nevét**.</span><span class="sxs-lookup"><span data-stu-id="bc3df-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="bc3df-159">Válassza ki a **Projekttípus**, **Projektcsoport** és a **Projektszerződés azonosítója** értékét.</span><span class="sxs-lookup"><span data-stu-id="bc3df-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="bc3df-160">Azt is megteheti, hogy létrehozhat új projektszerződést az **Új** elemre kattintva.</span><span class="sxs-lookup"><span data-stu-id="bc3df-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="bc3df-161">Válassza ki az erőforrásként használni kívánt **Naptárat**.</span><span class="sxs-lookup"><span data-stu-id="bc3df-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="bc3df-162">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bc3df-162">Click **OK**.</span></span>

