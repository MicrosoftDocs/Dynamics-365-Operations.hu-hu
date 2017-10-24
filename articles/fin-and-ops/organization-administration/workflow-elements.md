---
title: Munkafolyamat-elemek
description: "A cikk ismerteti a munkafolyamat különböző összetevőit."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 255777651a45b899850fc870c9da288f65df702c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="341dc-103">Munkafolyamat-elemek</span><span class="sxs-lookup"><span data-stu-id="341dc-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="341dc-104">A cikk ismerteti a munkafolyamat különböző összetevőit.</span><span class="sxs-lookup"><span data-stu-id="341dc-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="341dc-105">Egy munkafolyamat elemekből áll.</span><span class="sxs-lookup"><span data-stu-id="341dc-105">A workflow consists of elements.</span></span> <span data-ttu-id="341dc-106">A következő részek az elemek összes típusát.</span><span class="sxs-lookup"><span data-stu-id="341dc-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="341dc-107">Feladatok</span><span class="sxs-lookup"><span data-stu-id="341dc-107">Tasks</span></span>
<span data-ttu-id="341dc-108">A *feladat* egy olyan munkaegység, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="341dc-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="341dc-109">Kétféle típusú feladat adható hozzá egy munkafolyamathoz: manuális feladatok és automatizált feladatok.</span><span class="sxs-lookup"><span data-stu-id="341dc-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="341dc-110">Kézi feladat</span><span class="sxs-lookup"><span data-stu-id="341dc-110">Manual task</span></span>

<span data-ttu-id="341dc-111">A *manuális feladat* egy olyan munkaegység, amelyet a hozzárendelt felhasználónak kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="341dc-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="341dc-112">Például egy költségjelentési munkafolyamat tartalmazhat manuális feladatokat, amelyeknél a hozzárendelt felhasználóknak a következő műveleteket kell végrehajtaniuk:</span><span class="sxs-lookup"><span data-stu-id="341dc-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="341dc-113">Tekintse át a költségjelentésekkel együtt leadott nyugtákat.</span><span class="sxs-lookup"><span data-stu-id="341dc-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="341dc-114">Hívja az alkalmazott felettesét.</span><span class="sxs-lookup"><span data-stu-id="341dc-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="341dc-115">Automatizált feladat</span><span class="sxs-lookup"><span data-stu-id="341dc-115">Automated task</span></span>

<span data-ttu-id="341dc-116">Egy *automatizált feladat* egy olyan munkaegység, amelyet a rendszernek kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="341dc-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="341dc-117">Nincs szükség emberi beavatkozásra</span><span class="sxs-lookup"><span data-stu-id="341dc-117">No human interaction is required.</span></span> <span data-ttu-id="341dc-118">Például egy értékesítési jelentéshez tartozó munkafolyamat tartalmazhat automatizált feladatokat, amelyeknél a rendszernek a következő műveleteket kell végrehajtania:</span><span class="sxs-lookup"><span data-stu-id="341dc-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="341dc-119">Hitelkeret-ellenőrzés végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="341dc-119">Perform a credit check.</span></span>
-   <span data-ttu-id="341dc-120">Vevőrekord létrehozása a vevő számára, ha nem létezik még ilyen rekord.</span><span class="sxs-lookup"><span data-stu-id="341dc-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="341dc-121">Jóváhagyási folyamatok</span><span class="sxs-lookup"><span data-stu-id="341dc-121">Approval processes</span></span>
<span data-ttu-id="341dc-122">A *jóváhagyási folyamat* egy több lépésből álló folyamat.</span><span class="sxs-lookup"><span data-stu-id="341dc-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="341dc-123">Az egyes jóváhagyási lépésekkel a felhasználó a következő műveleteket végezheti el:</span><span class="sxs-lookup"><span data-stu-id="341dc-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="341dc-124">A dokumentum jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="341dc-124">Approve the document.</span></span>
-   <span data-ttu-id="341dc-125">A dokumentum elutasítása</span><span class="sxs-lookup"><span data-stu-id="341dc-125">Reject the document.</span></span>
-   <span data-ttu-id="341dc-126">A dokumentum módosításának kérése</span><span class="sxs-lookup"><span data-stu-id="341dc-126">Request a change to the document.</span></span>
-   <span data-ttu-id="341dc-127">A dokumentum másik felhasználóhoz rendelése jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="341dc-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="341dc-128">Sortétel munkafolyamatának elemei</span><span class="sxs-lookup"><span data-stu-id="341dc-128">Lineitem workflow elements</span></span>
<span data-ttu-id="341dc-129">Munkafolyamat létrehozható dokumentumok vagy a sorban szereplő cikkek egy dokumentumban való feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="341dc-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="341dc-130">Például létrehozott jóváhagyási munkafolyamatot időnyilvántartásokhoz.</span><span class="sxs-lookup"><span data-stu-id="341dc-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="341dc-131">(Erre a munkafolyamatra *dokumentum-munkafolyamat* néven fogunk hivatkozni.) Lehetőség van *egy sortétel-munkafolyamat* elem hozzáadásához a dokumentum-munkafolyamathoz.</span><span class="sxs-lookup"><span data-stu-id="341dc-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="341dc-132">A sortétel-elem futtatásakor a rendszer a dokumentumon szereplő minden sortételt elküld feldolgozásra.</span><span class="sxs-lookup"><span data-stu-id="341dc-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="341dc-133">Lehet, hogy az azonos sortétel-munkafolyamattal akarja feldolgoztatni a sorban szereplő cikkeket, vagy egy másik sortétel-munkafolyamattal szeretné feldolgoztatni a sorban szereplő cikkeket.</span><span class="sxs-lookup"><span data-stu-id="341dc-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="341dc-134">Tegyük fel, hogy az alkalmazott elküldött egy időnyilvántartást, amely hasonlít az alábbi ábrára.</span><span class="sxs-lookup"><span data-stu-id="341dc-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span>

![Munkafolyamat sortételekkel](./media/workflow_lineitemworkflow.gif) 

<span data-ttu-id="341dc-136">Ebben az esetben szükség lehet a következő sortétel-munkafolyamatok létrehozására:</span><span class="sxs-lookup"><span data-stu-id="341dc-136">In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="341dc-137">**Sortétel-munkafolyamat 1** – A munkafolyamat segítségével az 1111 projektazonosítójú sortételeket lehet feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="341dc-137">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="341dc-138">**Sortétel-munkafolyamat 2** – A munkafolyamat segítségével a 2222 projektazonosítójú sortételeket lehet feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="341dc-138">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="341dc-139">**Sortétel-munkafolyamat 3** – A munkafolyamat segítségével a 3333 projektazonosítójú sortételeket lehet feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="341dc-139">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="341dc-140">Vezérlési folyamat elemei</span><span class="sxs-lookup"><span data-stu-id="341dc-140">Flowcontrol elements</span></span>
<span data-ttu-id="341dc-141">A következő elemek lehetővé teszik, hogy olyan munkafolyamatokat tervezzen, amelyek másodlagos ágakkal vagy egyszerre futó ágakkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="341dc-141">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="341dc-142">Manuális döntés</span><span class="sxs-lookup"><span data-stu-id="341dc-142">Manual decision</span></span>

<span data-ttu-id="341dc-143">A *manuális döntés* egy olyan pont, ahol a munkafolyamat két ágra válik szét.</span><span class="sxs-lookup"><span data-stu-id="341dc-143">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="341dc-144">A felhasználónak végre kell hajtania a döntést, és ez a döntés határozza meg, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni.</span><span class="sxs-lookup"><span data-stu-id="341dc-144">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="341dc-145">Feltételes döntés</span><span class="sxs-lookup"><span data-stu-id="341dc-145">Conditional decision</span></span>

<span data-ttu-id="341dc-146">A *feltételes döntés* is egy olyan pont, ahol a munkafolyamat két ágra válik szét.</span><span class="sxs-lookup"><span data-stu-id="341dc-146">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="341dc-147">Azonban itt a rendszer dönt, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni.</span><span class="sxs-lookup"><span data-stu-id="341dc-147">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="341dc-148">Ahhoz, hogy ezt a döntést meghozza, a rendszer kiértékeli a dokumentumot, hogy meghatározza, hogy az megfelel-e meghatározott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="341dc-148">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="341dc-149">Párhuzamos tevékenység</span><span class="sxs-lookup"><span data-stu-id="341dc-149">Parallel activity</span></span>

<span data-ttu-id="341dc-150">A *párhuzamos tevékenység* egy olyan munkafolyamat-elem, amely két vagy több, egy időben futó munkafolyamatágat foglal magában.</span><span class="sxs-lookup"><span data-stu-id="341dc-150">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="341dc-151">Almunkafolyamat</span><span class="sxs-lookup"><span data-stu-id="341dc-151">Subworkflow</span></span>

<span data-ttu-id="341dc-152">Az *almunkafolyamat* egy olyan munkafolyamat, amely egy másik munkafolyamat kontextusán belül megy végbe.</span><span class="sxs-lookup"><span data-stu-id="341dc-152">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>



