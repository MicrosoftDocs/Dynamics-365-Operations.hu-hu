---
title: Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok
description: Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.
author: kamaybac
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd9ee69e180f2ff605c4f373a95d2346ccc73c0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807944"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="1d8bf-104">Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok</span><span class="sxs-lookup"><span data-stu-id="1d8bf-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d8bf-105">Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="1d8bf-106">A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="1d8bf-107">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-107">A workflow represents a business process.</span></span> <span data-ttu-id="1d8bf-108">Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="1d8bf-109">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="1d8bf-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="1d8bf-110">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="1d8bf-111">A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="1d8bf-112">**A folyamat láthatósága** – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="1d8bf-113">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="1d8bf-114">**Központi munkalista** – A felhasználók megtekinthetik a központi munkalistát, hogy lássák a munkafolyamat-feladatokat és jóváhagyásokat, amelyek hozzájuk vannak rendelve, minden olyan munkafolyamat során, amelyben részt vesznek.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="1d8bf-115">Ez a Munkatételek lapon érhető el.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="1d8bf-116"> A létrehozható munkafolyamat-típusok</span><span class="sxs-lookup"><span data-stu-id="1d8bf-116">The types of workflows that you can create</span></span>

<span data-ttu-id="1d8bf-117">A következő munkafolyamat-típusok elérhetőek a Beszerzés és forrás modulhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="1d8bf-118">Típus</span><span class="sxs-lookup"><span data-stu-id="1d8bf-118">Type</span></span> | <span data-ttu-id="1d8bf-119">Típus</span><span class="sxs-lookup"><span data-stu-id="1d8bf-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="1d8bf-120">Beszerzési igénylés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="1d8bf-120">Purchase requisition review</span></span> | <span data-ttu-id="1d8bf-121">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési igénylésekhez.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="1d8bf-122">Beszerzési igénylési sor ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="1d8bf-122">Purchase requisition line review</span></span> | <span data-ttu-id="1d8bf-123">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésiigénylés-sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="1d8bf-124">Beszerzési rendelés munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="1d8bf-124">Purchase order workflow</span></span> | <span data-ttu-id="1d8bf-125">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="1d8bf-126">Beszerzésirendelés-sor munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="1d8bf-126">Purchase order line workflow</span></span> | <span data-ttu-id="1d8bf-127">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésirendelés-sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="1d8bf-128">Szállítói hozzáadás alkalmazás-munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="1d8bf-128">Vendor add application workflow</span></span> | <span data-ttu-id="1d8bf-129">Ellenőrzési és jóváhagyási munkafolyamatok létrehozása új szállítók hozzáadásához a szállítói kérelmeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="1d8bf-130">Új munkafolyamat hozzáadásakor a következő elavult munkafolyamatok is megjelenhetnek a **Munkafolyamat létrehozása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="1d8bf-131">Ezek a korábban a [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows) szolgáltatásban elérhető *bevételezés megerősítése* funkcióhoz kapcsolódtak, amelyek mostanra elavultak.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="1d8bf-132">Ezek a munkafolyamatok jelenleg nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="1d8bf-133">Szállítási határidőkkel kapcsolatos értesítési munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="1d8bf-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="1d8bf-134">A számla megérkezéséről értesítő munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="1d8bf-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="1d8bf-135">A termékbevételezés során sikertelen volt az értesítési munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="1d8bf-136">Visszaigazolatlan termékbevételezés elutasításáról értesítő munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="1d8bf-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="1d8bf-137">Munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d8bf-137">Creating a workflow</span></span>

<span data-ttu-id="1d8bf-138">Hogy létrehozzon egy munkafolyamatot lépjen a Beszerzés és forrás &gt; Beállítás &gt; Beszerzés és forrás munkafolyamatok elemre és hozzon létre egy új munkafolyamatot a készíteni kívánt munkafolyamat-típus kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="1d8bf-139">A munkafolyamat vásznon behúzhatja a munkafolyamat elemeket a szerkesztőbe és bekapcsolhatja az elemeket egy folyamatba.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="1d8bf-140">A munkafolyamat-elemeket tanácsos konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-140">The workflow elements should be configured.</span></span> <span data-ttu-id="1d8bf-141">Jóváhagyás– és feladat munkafolyamat-elemekhez konfigurálhatja, hogy melyik résztvevőknek ajánlott cselekedniük.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="1d8bf-142">Résztvevőtípusok</span><span class="sxs-lookup"><span data-stu-id="1d8bf-142">Types of participants</span></span>

<span data-ttu-id="1d8bf-143">Jóváhagyási lépéseket rendelhet a következő résztvevőcsoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="1d8bf-144">Felhasználócsoport</span><span class="sxs-lookup"><span data-stu-id="1d8bf-144">User group</span></span> | <span data-ttu-id="1d8bf-145">Leírás</span><span class="sxs-lookup"><span data-stu-id="1d8bf-145">Description</span></span> |
|---|---|
| <span data-ttu-id="1d8bf-146">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="1d8bf-146">Participant</span></span> | <span data-ttu-id="1d8bf-147">A jóváhagyási lépés hozzárendelése egy csoport vagy szerepkör tagjaihoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="1d8bf-148">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="1d8bf-148">Hierarchy</span></span> | <span data-ttu-id="1d8bf-149">A jóváhagyási lépés hozzárendelése egy meghatározott szervezeti hierarchiában lévő felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="1d8bf-150">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="1d8bf-150">Workflow user</span></span> | <span data-ttu-id="1d8bf-151">A jóváhagyási lépés hozzárendelése a munkafolyamatban lévő felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="1d8bf-152">Várakozási sor</span><span class="sxs-lookup"><span data-stu-id="1d8bf-152">Queue</span></span> | <span data-ttu-id="1d8bf-153">Rendelje hozzá a jóváhagyási lépést egy munkatétel-várólistához.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="1d8bf-154">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="1d8bf-154">User</span></span> | <span data-ttu-id="1d8bf-155">Jóváhagyási lépés hozzárendelése adott felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="1d8bf-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="1d8bf-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1d8bf-156">Additional resources</span></span>

- [<span data-ttu-id="1d8bf-157">Üzleti folyamatok munkafolyamatainak meghatározása beszerzési igénylések számára</span><span class="sxs-lookup"><span data-stu-id="1d8bf-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="1d8bf-158">Beszerzési igénylési munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="1d8bf-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="1d8bf-159">Szállítók felvétele</span><span class="sxs-lookup"><span data-stu-id="1d8bf-159">Onboard vendors</span></span>](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]