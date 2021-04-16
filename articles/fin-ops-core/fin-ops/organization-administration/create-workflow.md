---
title: Munkafolyamatok létrehozása – áttekintés
description: Ez a témakör a munkafolyamat létrehozásának lépéseit mutatja be.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 1e1c86e828eef39a6895416f4825c2853e23c826
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747759"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="d4803-103">Munkafolyamatok létrehozása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="d4803-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4803-104">Ez a témakör a munkafolyamat létrehozásának lépéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d4803-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="d4803-105">A munkafolyamat-szerkesztő megnyitása</span><span class="sxs-lookup"><span data-stu-id="d4803-105">Open the workflow editor</span></span>

<span data-ttu-id="d4803-106">A modul, amelyben éppen dolgozik, meghatározza a létrehozható munkafolyamatokok típusát.</span><span class="sxs-lookup"><span data-stu-id="d4803-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="d4803-107">Ezekkel a lépésekkel válassza ki a létrehozni kívánt munkafolyamat-típust, és nyissa meg a munkafolyamat-szerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="d4803-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="d4803-108">Nyissa meg a modult, amelyhez új munkafolyamatot szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="d4803-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="d4803-109">Például egy beszerzési igénylés munkafolyamatának létrehozásához kattintson a **Beszerzés és forrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4803-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="d4803-110">Kattintson a **Beállítás** &gt; **\[Modulnév\]-munkafolyamatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="d4803-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="d4803-111">A megjelenő listaoldalon a műveleti ablaktáblán kattintson az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4803-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="d4803-112">A **Munkafolyamat létrehozása** oldalon válassza ki a létrehozandó munkafolyamatot, majd kattintson a **Munkafolyamat létrehozása** pontra.</span><span class="sxs-lookup"><span data-stu-id="d4803-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="d4803-113">A munkafolyamat-szerkesztő megjelenik.</span><span class="sxs-lookup"><span data-stu-id="d4803-113">The workflow editor appears.</span></span> <span data-ttu-id="d4803-114">A következő eljárásokkal lehet a munkafolyamatot megtervezni.</span><span class="sxs-lookup"><span data-stu-id="d4803-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="d4803-115">Munkafolyamat-elemek áthúzása a vászonra</span><span class="sxs-lookup"><span data-stu-id="d4803-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="d4803-116">**A munkafolyamat elemei** terület tartalmazza a munkafolyamathoz hozzáadható elemeket.</span><span class="sxs-lookup"><span data-stu-id="d4803-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="d4803-117">A munkafolyamat elemeinek hozzáadásához húzza azokat a vászonra.</span><span class="sxs-lookup"><span data-stu-id="d4803-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="d4803-118">Az elemek összekapcsolása</span><span class="sxs-lookup"><span data-stu-id="d4803-118">Connect the elements</span></span>

<span data-ttu-id="d4803-119">A munkafolyamat két elemének összekötéséhez tartsa az egérmutatót az egyik elem fölött, amíg a csatlakozási pontok meg nem jelennek.</span><span class="sxs-lookup"><span data-stu-id="d4803-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="d4803-120">Kattintson az egyik csatlakozási pontra, és húzza a másik elemhez.</span><span class="sxs-lookup"><span data-stu-id="d4803-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="d4803-121">Ügyeljen arra, hogy minden elemet összekössön.</span><span class="sxs-lookup"><span data-stu-id="d4803-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="d4803-122">A munkafolyamat tulajdonságainak beállítása</span><span class="sxs-lookup"><span data-stu-id="d4803-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="d4803-123">Az alábbi lépések segítségével állítsa be a munkafolyamat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="d4803-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="d4803-124">Kattintson a vászonra, és győződjön meg arról, hogy nincs munkafolyamat-elem kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="d4803-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="d4803-125">Kattintson a **Tulajdonságok** lehetőségre a **Tulajdonságok** lap megnyitásához az adott munkafolyamatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="d4803-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="d4803-126">Kövesse a [Munkafolyamat-tulajdonságok konfigurálása](configure-workflow-properties.md) cikkben leírt eljárásokat.</span><span class="sxs-lookup"><span data-stu-id="d4803-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="d4803-127">A munkafolyamat elemeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="d4803-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="d4803-128">Konfigurálja a vászonra áthúzott elemeket.</span><span class="sxs-lookup"><span data-stu-id="d4803-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="d4803-129">Ha további tudnivalókat szeretne az egyes munkafolyamat-elemek beállításáról, tekintse át az alábbi témaköröket:</span><span class="sxs-lookup"><span data-stu-id="d4803-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="d4803-130">Manuális feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="d4803-131">Automatizált feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="d4803-132">Jóváhagyási folyamatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="d4803-133">Jóváhagyási lépések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="d4803-134">Manuális döntések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="d4803-135">Feltételes döntések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="d4803-136">Párhuzamos ágak konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d4803-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="d4803-137">Párhuzamos ág konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d4803-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="d4803-138">Sortétel munkafolyamatainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d4803-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="d4803-139">Hibák vagy figyelmeztetések feloldása</span><span class="sxs-lookup"><span data-stu-id="d4803-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="d4803-140">A **Hibák és figyelmeztetések** ablaktáblán a munkafolyamat-szerkesztő alján a munkafolyamathoz generált üzenetek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="d4803-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="d4803-141">A hibaüzenettel vagy figyelmeztetéssel érintett elem megkereséséhez kattintson duplán a hibára vagy a figyelmeztetésre.</span><span class="sxs-lookup"><span data-stu-id="d4803-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="d4803-142">Az összes hibát és figyelmeztetést fel kell oldania, mielőtt aktiválhatja a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="d4803-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="d4803-143">A munkafolyamat mentése és aktiválása</span><span class="sxs-lookup"><span data-stu-id="d4803-143">Save and activate the workflow</span></span>

<span data-ttu-id="d4803-144">Ha készen áll a munkafolyamat mentésére és aktiválására, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d4803-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="d4803-145">Kattintson a **Mentés és bezárás** gombra a munkafolyamat-szerkesztő bezárásához, és a **Munkafolyamat mentése** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d4803-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="d4803-146">Írja be a munkafolyamat változtatásaihoz kapcsolódó megjegyzéseket, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d4803-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="d4803-147">Ha az összes hibát és figyelmeztetést feloldotta, megjelenik a **Munkafolyamat aktiválása** lap.</span><span class="sxs-lookup"><span data-stu-id="d4803-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="d4803-148">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="d4803-148">Select one of the following options:</span></span>

    - <span data-ttu-id="d4803-149">A munkafolyamat aktuális verziójának aktiválásához kattintson az **Új verzió aktiválása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4803-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="d4803-150">Ha egy munkafolyamat aktív, akkor a felhasználók dokumentumokat küldhetnek feldolgozásra.</span><span class="sxs-lookup"><span data-stu-id="d4803-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="d4803-151">Ha nem szeretné aktiválni ezt a verziót, kattintson a **Ne aktiválja az új verziót** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4803-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="d4803-152">A munkafolyamatot később is aktiválhatja.</span><span class="sxs-lookup"><span data-stu-id="d4803-152">You can activate the workflow later.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]