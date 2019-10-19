---
title: A munkafolyamat-rendszer áttekintése
description: Ez a témakör bemutatja a munkafolyamat rendszert.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e5e795ca6f7831ecd3fa28be9782f0b287eea6e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190005"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="0aec3-103">A munkafolyamat-rendszer áttekintése</span><span class="sxs-lookup"><span data-stu-id="0aec3-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0aec3-104">Ez a témakör bemutatja a munkafolyamat rendszert.</span><span class="sxs-lookup"><span data-stu-id="0aec3-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="0aec3-105">Mi az a munkafolyamat?</span><span class="sxs-lookup"><span data-stu-id="0aec3-105">What is workflow?</span></span>

<span data-ttu-id="0aec3-106">A *munkafolyamat* kifejezést kétféle módon lehet meghatározni: rendszerként és üzleti folyamatként.</span><span class="sxs-lookup"><span data-stu-id="0aec3-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="0aec3-107">A munkafolyamat egy rendszer</span><span class="sxs-lookup"><span data-stu-id="0aec3-107">Workflow is a system</span></span>

<span data-ttu-id="0aec3-108">A munkafolyamat olyan rendszer, amely az Application Object Server (AOS) kiszolgálón fut.</span><span class="sxs-lookup"><span data-stu-id="0aec3-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="0aec3-109">A munkafolyamat rendszer egy olyan funkciót biztosít, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.</span><span class="sxs-lookup"><span data-stu-id="0aec3-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="0aec3-110">A munkafolyamat egy üzleti eljárás</span><span class="sxs-lookup"><span data-stu-id="0aec3-110">Workflow is a business process</span></span>

<span data-ttu-id="0aec3-111">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="0aec3-111">A workflow represents a business process.</span></span> <span data-ttu-id="0aec3-112">Azt határozza meg, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="0aec3-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="0aec3-113">Az alábbi illusztráció szemlélteti a költségjelentések munkafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="0aec3-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Munkafolyamat felhasználókhoz rendelt elemekkel](./media/workflow_user.gif)

<span data-ttu-id="0aec3-115">A munkafolyamat könnyebb megértésének érdekében tegyük fel, hogy Balázs benyújt egy 7000 dolláros költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="0aec3-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="0aec3-116">Ebben az esetben Ivánnak ellenőriznie kell a számlákat, amelyeket Sam irányított hozzá.</span><span class="sxs-lookup"><span data-stu-id="0aec3-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="0aec3-117">Ezt követően Ferencnek és Zsuzsannának jóvá kell hagynia a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="0aec3-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="0aec3-118">Ezután tegyük fel, hogy Sam benyújt egy újabb költségjelentést, ezúttal 11 000 dollárról.</span><span class="sxs-lookup"><span data-stu-id="0aec3-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="0aec3-119">Ebben az esetben Ivánnak ellenőriznie kell a nyugtákat, majd Ferencnek, Zsuzsannának és Annának is jóvá kell hagynia a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="0aec3-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="0aec3-120"> A munkafolyamat rendszer használatának előnyei</span><span class="sxs-lookup"><span data-stu-id="0aec3-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="0aec3-121">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="0aec3-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="0aec3-122">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok, például a beszerzési igénylések és költségjelentések feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="0aec3-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="0aec3-123">A munkafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="0aec3-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="0aec3-124">**A folyamat láthatósága** – Nyomon követheti a munkafolyamat-példányok állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="0aec3-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="0aec3-125">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="0aec3-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="0aec3-126">**Központi munkalista** – a felhasználók centralizált munkalistát tekinthetnek meg, amely megjeleníti a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.</span><span class="sxs-lookup"><span data-stu-id="0aec3-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="0aec3-127">Munkafolyamat-tartalom</span><span class="sxs-lookup"><span data-stu-id="0aec3-127">Workflow content</span></span>

+ [<span data-ttu-id="0aec3-128">Munkafolyamat felépítése</span><span class="sxs-lookup"><span data-stu-id="0aec3-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="0aec3-129">Munkafolyamat-elemek</span><span class="sxs-lookup"><span data-stu-id="0aec3-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="0aec3-130">Munkafolyamat-műveletek</span><span class="sxs-lookup"><span data-stu-id="0aec3-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="0aec3-131">Munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="0aec3-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="0aec3-132">Munkafolyamat-tulajdonságok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0aec3-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="0aec3-133">Manuális feladat konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="0aec3-134">Automatikus feladat konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="0aec3-135">Jóváhagyási folyamat konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="0aec3-136">Jóváhagyási lépés konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="0aec3-137">Manuális döntés konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="0aec3-138">Feltételes döntés konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="0aec3-139">Párhuzamos tevékenység beállítása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="0aec3-140">Párhuzamos ágának konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="0aec3-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="0aec3-141">Sortétel munkafolyamatának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0aec3-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="0aec3-142">Munkafolyamat GYIK</span><span class="sxs-lookup"><span data-stu-id="0aec3-142">Workflow FAQ</span></span>](workflow-FAQ.md)
