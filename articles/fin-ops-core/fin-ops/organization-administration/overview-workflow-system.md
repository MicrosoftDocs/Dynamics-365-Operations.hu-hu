---
title: A munkafolyamat-rendszer áttekintése
description: Ez a témakör bemutatja a munkafolyamat rendszert.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796996"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="45b5c-103">A munkafolyamat-rendszer áttekintése</span><span class="sxs-lookup"><span data-stu-id="45b5c-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45b5c-104">Ez a témakör bemutatja a munkafolyamat rendszert.</span><span class="sxs-lookup"><span data-stu-id="45b5c-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="45b5c-105">Mi az a munkafolyamat?</span><span class="sxs-lookup"><span data-stu-id="45b5c-105">What is workflow?</span></span>

<span data-ttu-id="45b5c-106">A *munkafolyamat* kifejezést kétféle módon lehet meghatározni: rendszerként és üzleti folyamatként.</span><span class="sxs-lookup"><span data-stu-id="45b5c-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="45b5c-107">A munkafolyamat egy rendszer</span><span class="sxs-lookup"><span data-stu-id="45b5c-107">Workflow is a system</span></span>

<span data-ttu-id="45b5c-108">A munkafolyamat olyan rendszer, amely az Application Object Server (AOS) kiszolgálón fut.</span><span class="sxs-lookup"><span data-stu-id="45b5c-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="45b5c-109">A munkafolyamat rendszer egy olyan funkciót biztosít, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.</span><span class="sxs-lookup"><span data-stu-id="45b5c-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="45b5c-110">A munkafolyamat egy üzleti eljárás</span><span class="sxs-lookup"><span data-stu-id="45b5c-110">Workflow is a business process</span></span>

<span data-ttu-id="45b5c-111">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="45b5c-111">A workflow represents a business process.</span></span> <span data-ttu-id="45b5c-112">Azt határozza meg, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="45b5c-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="45b5c-113">Az alábbi illusztráció szemlélteti a költségjelentések munkafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="45b5c-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Munkafolyamat felhasználókhoz rendelt elemekkel](./media/workflow_user.gif)

<span data-ttu-id="45b5c-115">A munkafolyamat könnyebb megértésének érdekében tegyük fel, hogy Balázs benyújt egy 7000 dolláros költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="45b5c-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="45b5c-116">Ebben az esetben Ivánnak ellenőriznie kell a számlákat, amelyeket Sam irányított hozzá.</span><span class="sxs-lookup"><span data-stu-id="45b5c-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="45b5c-117">Ezt követően Ferencnek és Zsuzsannának jóvá kell hagynia a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="45b5c-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="45b5c-118">Ezután tegyük fel, hogy Sam benyújt egy újabb költségjelentést, ezúttal 11 000 dollárról.</span><span class="sxs-lookup"><span data-stu-id="45b5c-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="45b5c-119">Ebben az esetben Ivánnak ellenőriznie kell a nyugtákat, majd Ferencnek, Zsuzsannának és Annának is jóvá kell hagynia a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="45b5c-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="45b5c-120"> A munkafolyamat rendszer használatának előnyei</span><span class="sxs-lookup"><span data-stu-id="45b5c-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="45b5c-121">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="45b5c-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="45b5c-122">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok, például a beszerzési igénylések és költségjelentések feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="45b5c-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="45b5c-123">A munkafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="45b5c-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="45b5c-124">**A folyamat láthatósága** – Nyomon követheti a munkafolyamat-példányok állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="45b5c-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="45b5c-125">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="45b5c-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="45b5c-126">**Központi munkalista** – a felhasználók centralizált munkalistát tekinthetnek meg, amely megjeleníti a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.</span><span class="sxs-lookup"><span data-stu-id="45b5c-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="45b5c-127">Munkafolyamat-tartalom</span><span class="sxs-lookup"><span data-stu-id="45b5c-127">Workflow content</span></span>

+ [<span data-ttu-id="45b5c-128">A munkafolyamat-rendszer felépítése</span><span class="sxs-lookup"><span data-stu-id="45b5c-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="45b5c-129">Munkafolyamat-elemek</span><span class="sxs-lookup"><span data-stu-id="45b5c-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="45b5c-130">Munkafolyamat-jóváhagyási folyamatok műveletei</span><span class="sxs-lookup"><span data-stu-id="45b5c-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="45b5c-131">Munkafolyamatok létrehozása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="45b5c-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="45b5c-132">Munkafolyamat-tulajdonságok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="45b5c-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="45b5c-133">Manuális feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="45b5c-134">Automatizált feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="45b5c-135">Jóváhagyási folyamatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="45b5c-136">Jóváhagyási lépések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="45b5c-137">Manuális döntések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="45b5c-138">Feltételes döntések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="45b5c-139">Párhuzamos tevékenységek beállítása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="45b5c-140">Párhuzamos ágak konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="45b5c-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="45b5c-141">Sortétel munkafolyamatainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="45b5c-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="45b5c-142">Munkafolyamat GYIK</span><span class="sxs-lookup"><span data-stu-id="45b5c-142">Workflow FAQ</span></span>](workflow-FAQ.md)
