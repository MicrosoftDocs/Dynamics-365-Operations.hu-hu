---
title: Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok
description: Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ceab555bf278ced13d8360956f6db65ba275f8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813454"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="03d51-104">Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok</span><span class="sxs-lookup"><span data-stu-id="03d51-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03d51-105">Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó.</span><span class="sxs-lookup"><span data-stu-id="03d51-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="03d51-106">A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="03d51-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="03d51-107">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="03d51-107">A workflow represents a business process.</span></span> <span data-ttu-id="03d51-108">Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="03d51-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="03d51-109">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="03d51-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="03d51-110">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét.</span><span class="sxs-lookup"><span data-stu-id="03d51-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="03d51-111">A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="03d51-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="03d51-112">**A folyamat láthatósága** – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="03d51-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="03d51-113">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="03d51-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="03d51-114">**Központi munkalista** – A felhasználók megtekinthetik a központi munkalistát, hogy lássák a munkafolyamat-feladatokat és jóváhagyásokat, amelyek hozzájuk vannak rendelve, minden olyan munkafolyamat során, amelyben részt vesznek.</span><span class="sxs-lookup"><span data-stu-id="03d51-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="03d51-115">Ez a Munkatételek lapon érhető el.</span><span class="sxs-lookup"><span data-stu-id="03d51-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="03d51-116"> A létrehozható munkafolyamat-típusok</span><span class="sxs-lookup"><span data-stu-id="03d51-116">The types of workflows that you can create</span></span>
<span data-ttu-id="03d51-117">A következő munkafolyamat-típusok elérhetőek a Beszerzés és forrás modulhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="03d51-118">**Típus**</span><span class="sxs-lookup"><span data-stu-id="03d51-118">**Type**</span></span>                         | <span data-ttu-id="03d51-119">**Típus**</span><span class="sxs-lookup"><span data-stu-id="03d51-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="03d51-120">Beszerzési igénylés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="03d51-120">Purchase requisition review</span></span>      | <span data-ttu-id="03d51-121">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési igénylésekhez.</span><span class="sxs-lookup"><span data-stu-id="03d51-121">Create review and approval workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="03d51-122">Beszerzési igénylési sor ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="03d51-122">Purchase requisition line review</span></span> | <span data-ttu-id="03d51-123">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésiigénylés-sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-123">Create review and approval workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="03d51-124">Beszerzési rendelés munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="03d51-124">Purchase order workflow</span></span>          | <span data-ttu-id="03d51-125">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="03d51-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="03d51-126">Beszerzésirendelés-sor munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="03d51-126">Purchase order line workflow</span></span>     | <span data-ttu-id="03d51-127">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésirendelés-sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="03d51-128">Szállítói hozzáadás alkalmazás-munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="03d51-128">Vendor add application workflow</span></span>  | <span data-ttu-id="03d51-129">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása új szállítók hozzáadásához a szállítói kérelmeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="03d51-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="03d51-130">Munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="03d51-130">Creating a workflow</span></span>

<span data-ttu-id="03d51-131">Hogy létrehozzon egy munkafolyamatot lépjen a Beszerzés és forrás &gt; Beállítás &gt; Beszerzés és forrás munkafolyamatok elemre és hozzon létre egy új munkafolyamatot a készíteni kívánt munkafolyamat-típus kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="03d51-131">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="03d51-132">A munkafolyamat vásznon behúzhatja a munkafolyamat elemeket a szerkesztőbe és bekapcsolhatja az elemeket egy folyamatba.</span><span class="sxs-lookup"><span data-stu-id="03d51-132">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="03d51-133">A munkafolyamat-elemeket tanácsos konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="03d51-133">The workflow elements should be configured.</span></span> <span data-ttu-id="03d51-134">Jóváhagyás– és feladat munkafolyamat-elemekhez konfigurálhatja, hogy melyik résztvevőknek ajánlott cselekedniük.</span><span class="sxs-lookup"><span data-stu-id="03d51-134">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="03d51-135">Résztvevőtípusok</span><span class="sxs-lookup"><span data-stu-id="03d51-135">Types of participants</span></span>

<span data-ttu-id="03d51-136">Jóváhagyási lépéseket rendelhet a következő résztvevőcsoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-136">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="03d51-137">Felhasználócsoport</span><span class="sxs-lookup"><span data-stu-id="03d51-137">User group</span></span>    | <span data-ttu-id="03d51-138">Leírás</span><span class="sxs-lookup"><span data-stu-id="03d51-138">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="03d51-139">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="03d51-139">Participant</span></span>   | <span data-ttu-id="03d51-140">A jóváhagyási lépés hozzárendelése egy csoport vagy szerepkör tagjaihoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-140">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="03d51-141">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="03d51-141">Hierarchy</span></span>     | <span data-ttu-id="03d51-142">A jóváhagyási lépés hozzárendelése egy meghatározott szervezeti hierarchiában lévő felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-142">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="03d51-143">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="03d51-143">Workflow user</span></span> | <span data-ttu-id="03d51-144">A jóváhagyási lépés hozzárendelése a munkafolyamatban lévő felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-144">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="03d51-145">Várakozási sor</span><span class="sxs-lookup"><span data-stu-id="03d51-145">Queue</span></span>         | <span data-ttu-id="03d51-146">Rendelje hozzá a jóváhagyási lépést egy munkatétel-várólistához.</span><span class="sxs-lookup"><span data-stu-id="03d51-146">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="03d51-147">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="03d51-147">User</span></span>          | <span data-ttu-id="03d51-148">Jóváhagyási lépés hozzárendelése adott felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="03d51-148">Assign the approval step to specific users.</span></span>                               |



## <a name="additional-resources"></a><span data-ttu-id="03d51-149">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="03d51-149">Additional resources</span></span>

- [<span data-ttu-id="03d51-150">Üzleti folyamatok munkafolyamatainak meghatározása beszerzési igénylések számára</span><span class="sxs-lookup"><span data-stu-id="03d51-150">Defining business process workflows for purchase requisitions</span></span>](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

- [<span data-ttu-id="03d51-151">Beszerzési igénylési munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="03d51-151">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)

- [<span data-ttu-id="03d51-152">Szállítók felvétele</span><span class="sxs-lookup"><span data-stu-id="03d51-152">Onboard vendors</span></span>](vendor-onboarding.md)

