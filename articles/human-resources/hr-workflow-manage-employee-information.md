---
title: Alkalmazotti adatok kezelése munkafolyamatok segítségével
description: Ez a cikk bemutatja, hogy miként használhatja az Emberi erőforrások munkafolyamatait az alkalmazottak információinak kezelésére. Például egy munkafolyamatot társíthat egy pozícióhoz, és konfigurálhat egy jóváhagyási munkafolyamatot, amely akkor kezdődik, amikor az alkalmazottak módosítják a rekordjaikat.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: aba7627877cd9b79dce5930e528f892e2d80baac
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058752"
---
# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="999db-104">Alkalmazotti adatok kezelése munkafolyamatok segítségével</span><span class="sxs-lookup"><span data-stu-id="999db-104">Use workflows to manage employee information</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="999db-105">Ez a cikk bemutatja, hogy miként használhatja az Emberi erőforrások munkafolyamatait az alkalmazottak információinak kezelésére.</span><span class="sxs-lookup"><span data-stu-id="999db-105">This article explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="999db-106">Például egy munkafolyamatot társíthat egy pozícióhoz, és konfigurálhat egy jóváhagyási munkafolyamatot, amely akkor kezdődik, amikor az alkalmazottak módosítják a rekordjaikat.</span><span class="sxs-lookup"><span data-stu-id="999db-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="999db-107">Az Emberi erőforrások munkafolyamat-lehetőségei számos munkafolyamatot biztosítanak az emberierőforrás-tevékenységek kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="999db-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="999db-108">Ezenkívül számos opció áll rendelkezésre, hogy bizonyos munkafolyamatokat módosíthasson, és társíthassa azokat egy jelentéshierarchiához.</span><span class="sxs-lookup"><span data-stu-id="999db-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="999db-109">Munkafolyamatok állnak rendelkezésre, amelyek segítenek számos szabványos alkalmazottinformáció-típus változásainak kezelésében.</span><span class="sxs-lookup"><span data-stu-id="999db-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="999db-110">A munkafolyamatok beosztásokkal társíthatók.</span><span class="sxs-lookup"><span data-stu-id="999db-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="999db-111">Ha az alkalmazottak ezután megváltoztatják az alkalmazotti rekordjukat, akkor elindul egy munkafolyamat, amely jóváhagyást igényel az új információk mentése előtt.</span><span class="sxs-lookup"><span data-stu-id="999db-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="999db-112">A munkafolyamatok előre definiálva vannak az alábbi típusú információkhoz, amelyek segítenek hatékonyan kezelni a változásokat, illetve megőrizni az alkalmazottak adatainak pontosságát:</span><span class="sxs-lookup"><span data-stu-id="999db-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="999db-113">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="999db-113">Identification numbers</span></span>
-   <span data-ttu-id="999db-114">Tanfolyamok</span><span class="sxs-lookup"><span data-stu-id="999db-114">Courses</span></span>
-   <span data-ttu-id="999db-115">Végzettség</span><span class="sxs-lookup"><span data-stu-id="999db-115">Education</span></span>
-   <span data-ttu-id="999db-116">Kép</span><span class="sxs-lookup"><span data-stu-id="999db-116">Image</span></span>
-   <span data-ttu-id="999db-117">Kölcsönzött cikkek</span><span class="sxs-lookup"><span data-stu-id="999db-117">Loaned items</span></span>
-   <span data-ttu-id="999db-118">Szakmai tapasztalat</span><span class="sxs-lookup"><span data-stu-id="999db-118">Professional experience</span></span>
-   <span data-ttu-id="999db-119">Projekttapasztalat</span><span class="sxs-lookup"><span data-stu-id="999db-119">Project experience</span></span>
-   <span data-ttu-id="999db-120">Szakértelem</span><span class="sxs-lookup"><span data-stu-id="999db-120">Skills</span></span>
-   <span data-ttu-id="999db-121">Bizalmi beosztások</span><span class="sxs-lookup"><span data-stu-id="999db-121">Positions of trust</span></span>
-   <span data-ttu-id="999db-122">Emberi erőforrásokkal kapcsolatos műveletek</span><span class="sxs-lookup"><span data-stu-id="999db-122">Human resources actions</span></span>
-   <span data-ttu-id="999db-123">Tanfolyami regisztráció</span><span class="sxs-lookup"><span data-stu-id="999db-123">Course registration</span></span>

<span data-ttu-id="999db-124">Alkalmazottak felvétele, áthelyezése vagy elbocsátása esetén a munkafolyamat felülvizsgálati folyamatot is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="999db-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="999db-125">Ily módon egy-egy dokumentum felülvizsgálható, illetve egy művelet feltételei a munkafolyamat részeként határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="999db-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="999db-126">Az ellenőrzési folyamat befejezése után a dokumentum vagy a művelet befejeződik, és a munkafolyamat egy végső jóváhagyási lépéshez kerül.</span><span class="sxs-lookup"><span data-stu-id="999db-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="999db-127">Munkafolyamatok társítása beosztáshierarchiával</span><span class="sxs-lookup"><span data-stu-id="999db-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="999db-128">A munkafolyamatot egy tetszőleges, Ön által konfigurált hierarchiához társíthatja.</span><span class="sxs-lookup"><span data-stu-id="999db-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="999db-129">Ha például egy pozíció egy mátrixjelentési hierarchiához társul, akkor konfigurálhat egy olyan munkafolyamatot, amely egy adott projekt költségeit a projektvezetőhöz irányítja az adott pozícióhoz társított munkavállaló vezetője helyett.</span><span class="sxs-lookup"><span data-stu-id="999db-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="999db-130">Új munkafolyamat létrehozásához, illetve meglévő módosításához kattintson az **Emberi erőforrások munkafolyamata** lapon az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="999db-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="999db-131">Válasszon ki egy munkafolyamatot a listából a Munkafolyamat-tervező elindításához.</span><span class="sxs-lookup"><span data-stu-id="999db-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="999db-132">A tervező segítségével új munkafolyamatot hozhat létre, illetve módosíthatja egy meglévő munkafolyamat lépéseit.</span><span class="sxs-lookup"><span data-stu-id="999db-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="999db-133">Amikor módosít egy meglévő munkafolyamatot, a módosításai új verzióként kerülnek mentésre.</span><span class="sxs-lookup"><span data-stu-id="999db-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="999db-134">Így szükség esetén bármikor visszatérhet egy korábbi verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="999db-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="999db-135">Emberi erőforrások munkafolyamatának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="999db-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="999db-136">Ha konfigurálni szeretne egy alapvető munkafolyamatot, amelyik akkor indul el, amikor az alkalmazottak személyes azonosítójuk módosításait kérik, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="999db-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="999db-137">Az **Emberi erőforrások munkafolyamatai** lapon kattintson az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="999db-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="999db-138">Válassza ki a rendelkezésre álló munkafolyamatok listájánál az **Azonosítószámok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="999db-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="999db-139">Kattintson a **Futtatás** lehetőségre a Munkafolyamat-tervező elindításához, majd adja meg a felhasználónevet és a jelszót, amikor a rendszer erre kéri.</span><span class="sxs-lookup"><span data-stu-id="999db-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="999db-140">Húzza az **Azonosítószám jóváhagyása** elemet a munkafolyamat-elemek listájáról a tervezői vászonra.</span><span class="sxs-lookup"><span data-stu-id="999db-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="999db-141">Csatlakoztassa a jóváhagyási elemet a **Kezdés** és **Befejezés** pontokhoz.</span><span class="sxs-lookup"><span data-stu-id="999db-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="999db-142">Kattintson duplán az **Elem jóváhagyása** pontra, majd kattintson a jobb gombra, és válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="999db-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="999db-143">Kövesse az alábbi lépéseket a munkatétel hozzáadásához:</span><span class="sxs-lookup"><span data-stu-id="999db-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="999db-144">Válassza ki a **Hozzárendelés** elemet, majd a **Hierarchia** lehetőséget a hozzárendelés típusánál.</span><span class="sxs-lookup"><span data-stu-id="999db-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="999db-145">A **Hierarchia** kijelölés alatt válassza ki a **Konfigurálható hierarchia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="999db-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="999db-146">Adja hozzá a leállási feltételt, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="999db-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="999db-147">Töltse ki a további utasításokat (ne maradjanak további figyelmeztetések).</span><span class="sxs-lookup"><span data-stu-id="999db-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="999db-148">Kattintson a **Mentés és bezárás** pontra.</span><span class="sxs-lookup"><span data-stu-id="999db-148">Click **Save and close**.</span></span> <span data-ttu-id="999db-149">Aktiválja az új munkafolyamatot, amikor megnyílik a párbeszédpanel, és válassza ki a **Legyen aktív** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="999db-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="999db-150">Lépjen az **Emberi erőforrások** &gt; **Beosztások** &gt; **Beosztáshierarchia-típusok** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="999db-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="999db-151">Válassza ki a **Mátrix** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="999db-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="999db-152">Adja hozzá a **Dolgozó azonosítószáma** munkafolyamatot a listához.</span><span class="sxs-lookup"><span data-stu-id="999db-152">Add the **Worker identification number** workflow to the list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="999db-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="999db-153">Additional resources</span></span>

[<span data-ttu-id="999db-154">A cím változásainak megtekintése és kezelése</span><span class="sxs-lookup"><span data-stu-id="999db-154">View and manage address changes</span></span>](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]