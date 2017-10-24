---
title: "Munkafolyamat-műveletek"
description: "Ez a cikk ismerteti a munkafolyamat elfogadási folyamatának egyes résztvevői által vállalható műveleteket."
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
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bbaac72d8adb764c4b186b022100248b1c5a3804
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-actions"></a><span data-ttu-id="c6160-103">Munkafolyamat-műveletek</span><span class="sxs-lookup"><span data-stu-id="c6160-103">Workflow actions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c6160-104">Ez a cikk ismerteti a munkafolyamat elfogadási folyamatának egyes résztvevői által vállalható műveleteket.</span><span class="sxs-lookup"><span data-stu-id="c6160-104">This article explains the actions that each participant in a workflow approval process can take.</span></span>

<span data-ttu-id="c6160-105">A munkafolyamat több csoportot is tartalmazhat: a létrehozó, a feladathoz hozzárendelt személyek, döntéshozók, valamint jóváhagyók.</span><span class="sxs-lookup"><span data-stu-id="c6160-105">A workflow can involve several groups of people: the originator, task assignees, decision makers, and approvers.</span></span> <span data-ttu-id="c6160-106">Például, az alábbi a költségjelentés munkafolyamatánál Balázs a létrehozó, a várólista tagjai a hozzárendelt személyek, János a döntéshozó, illetve Ferenc, Zsuzsanna és Anna a jóváhagyók.</span><span class="sxs-lookup"><span data-stu-id="c6160-106">For example, in the following expense report workflow, Sam is the originator, the members of the queue are task assignees, John is a decision maker, and Frank, Sue, and Ann are approvers.</span></span>   

<span data-ttu-id="c6160-107">[![Munkafolyamat\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)</span><span class="sxs-lookup"><span data-stu-id="c6160-107">[![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)</span></span> 

<span data-ttu-id="c6160-108">Az alábbi szakaszok leírják az egyes csoportok által a munkafolyamatban végrehajtható műveleteket.</span><span class="sxs-lookup"><span data-stu-id="c6160-108">The following sections explain the workflow actions that each group can perform.</span></span>

## <a name="actions-that-an-originator-can-perform"></a><span data-ttu-id="c6160-109">A létrehozó által végrehajtható műveletek</span><span class="sxs-lookup"><span data-stu-id="c6160-109">Actions that an originator can perform</span></span>
<span data-ttu-id="c6160-110">A létrehozó a munkafolyamat egy példányát dokumentum feldolgozásra vagy jóváhagyásra történő elküldésével indítja el.</span><span class="sxs-lookup"><span data-stu-id="c6160-110">The originator starts a workflow instance by submitting a document for processing.</span></span> <span data-ttu-id="c6160-111">Például, Balázs kattintson a **Küldés** gombra a **Költségjelentés** lapon, hogy benyújtsa a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c6160-111">For example, Sam must click the **Submit** button on the **Expense report** page to submit his expense report.</span></span>

## <a name="actions-that-a-task-assignee-can-perform"></a><span data-ttu-id="c6160-112">A feladat megbízottja által végrehajtható műveletek</span><span class="sxs-lookup"><span data-stu-id="c6160-112">Actions that a task assignee can perform</span></span>
<span data-ttu-id="c6160-113">Egy feladatot végezhet több személy, vagy egy munkatétel-várólista, amit néhány ember felügyel.</span><span class="sxs-lookup"><span data-stu-id="c6160-113">A task can be assigned to multiple people or to a work item queue that is monitored by several people.</span></span> <span data-ttu-id="c6160-114">Azonban egy feladatot csak egy ember fejezhet be.</span><span class="sxs-lookup"><span data-stu-id="c6160-114">However, only one person can complete a task.</span></span> <span data-ttu-id="c6160-115">Például Balázs elküldött egy költségjelentést, és a nyugtáit a szervezetének költségjelentési részlegébe küldte ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="c6160-115">For example, Sam has submitted an expense report and has routed his receipts to his organization's Expense Reports department for review.</span></span> 

<span data-ttu-id="c6160-116">A Kalandorbolt költségjelentési részlegének tagjai követik nyomon a várólistát.</span><span class="sxs-lookup"><span data-stu-id="c6160-116">The members of the Adventure Works Expense Reports department monitor the queue.</span></span> <span data-ttu-id="c6160-117">Ágnes, annak a részlegnek az egyik tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségjelentését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-117">Julie, a member of that department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="c6160-118">A következő műveletek egyikét hajthatja most végre: elutasíthatja, delegálhatja, módosíthatja a kérést, újra hozzárendelhet vagy kiadhatja.</span><span class="sxs-lookup"><span data-stu-id="c6160-118">She can now perform one of the following actions: complete, reject, delegate, request change, reassign, or release.</span></span> 

<span data-ttu-id="c6160-119">**Megjegyzés:** Az elérhető műveletek változhatnak, attól függően, hogy a szoftverfejlesztő hogyan tervezte meg a feladatot.</span><span class="sxs-lookup"><span data-stu-id="c6160-119">**Note:** The actions that are available vary, depending on how the software developer designed the task.</span></span>

### <a name="complete"></a><span data-ttu-id="c6160-120">Befejezés</span><span class="sxs-lookup"><span data-stu-id="c6160-120">Complete</span></span>

<span data-ttu-id="c6160-121">Amikor egy felhasználó befejez egy feladatot, a feldolgozásra küldött dokumentumot a rendszer szükség esetén a munkafolyamat következő felhasználójához rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="c6160-121">When a user completes a task, the document that was submitted for processing is assigned to the next user in the workflow, if there is a next user.</span></span> <span data-ttu-id="c6160-122">Amennyiben nincs szükség további feldolgozásra, a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="c6160-122">If no additional processing is required, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-123">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-123">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam’s expense report and receipts.</span></span> <span data-ttu-id="c6160-124">Miután Ágnes befejezte az ellenőrzést, a dokumentum Jánoshoz kerül.</span><span class="sxs-lookup"><span data-stu-id="c6160-124">After Julie completes her review, the document is assigned to John.</span></span>

### <a name="reject"></a><span data-ttu-id="c6160-125">Elutasítás</span><span class="sxs-lookup"><span data-stu-id="c6160-125">Reject</span></span>

<span data-ttu-id="c6160-126">Amikor egy felhasználó elutasítja a dokumentumot, a munkafolyamat véget ér.</span><span class="sxs-lookup"><span data-stu-id="c6160-126">When a user rejects a document, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-127">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-127">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam’s expense report and receipts.</span></span> <span data-ttu-id="c6160-128">Ha Ágnes visszautasítja a költségjelentést, a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="c6160-128">If Julie rejects the expense report, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-129">Balázs ezután újraküldheti a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c6160-129">Sam can then resubmit the expense report.</span></span> <span data-ttu-id="c6160-130">Akkor módosíthatja is először, vagy dönthet úgy, hogy újraküldi az eredeti verziót.</span><span class="sxs-lookup"><span data-stu-id="c6160-130">He can make changes first, or he can resubmit the original version.</span></span> <span data-ttu-id="c6160-131">Ha Balázs újraküldi a költségjelentést, akkor a munkafolyamat a manuális ellenőrzési folyamatnál kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c6160-131">If Sam resubmits the expense report, the workflow process starts at the manual review task.</span></span>

### <a name="delegate"></a><span data-ttu-id="c6160-132">Delegált</span><span class="sxs-lookup"><span data-stu-id="c6160-132">Delegate</span></span>

<span data-ttu-id="c6160-133">Amikor egy felhasználó feladatot delegál, másik felhasználóhoz rendeli hozzá a feladatot.</span><span class="sxs-lookup"><span data-stu-id="c6160-133">When a user delegates a task, the task is assigned to another user.</span></span> 

<span data-ttu-id="c6160-134">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-134">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="c6160-135">Ágnes ezt a feladatot Timihez delegálja, aki az ő asszisztense.</span><span class="sxs-lookup"><span data-stu-id="c6160-135">Julie delegates this task to Tim, who is her assistant.</span></span> 

<span data-ttu-id="c6160-136">Timi ezután Ágnes nevében jár el.</span><span class="sxs-lookup"><span data-stu-id="c6160-136">Tim then acts on behalf of Julie.</span></span> <span data-ttu-id="c6160-137">Ezért mikor Timi befejezi az ellenőrzést, a költségjelentés Jánoshoz kerül, mintha Ágnes fejezte volna be a feladatot.</span><span class="sxs-lookup"><span data-stu-id="c6160-137">Therefore, when Tim completes his review, the expense report is assigned to John, just as if Julie had completed the task.</span></span>

### <a name="request-change"></a><span data-ttu-id="c6160-138">Változtatás kérése</span><span class="sxs-lookup"><span data-stu-id="c6160-138">Request change</span></span>

<span data-ttu-id="c6160-139">Amikor az egyik felhasználó az elküldött dokumentum változtatását kéri, a dokumentumot visszaküldi a rendszer a létrehozónak.</span><span class="sxs-lookup"><span data-stu-id="c6160-139">When a user requests a change to a document that was submitted, the document is sent back to the originator.</span></span> 

<span data-ttu-id="c6160-140">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-140">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="c6160-141">Ágnes talál néhány hibát a jelentésben, ezért változtatásokat kér.</span><span class="sxs-lookup"><span data-stu-id="c6160-141">Julie notices some errors on the expense report and requests changes.</span></span> <span data-ttu-id="c6160-142">A költségjelentés visszakerül Balázshoz.</span><span class="sxs-lookup"><span data-stu-id="c6160-142">The expense report is sent back to Sam.</span></span> 

<span data-ttu-id="c6160-143">Balázs ezután újraküldheti a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c6160-143">Sam can resubmit the expense report.</span></span> <span data-ttu-id="c6160-144">Elvégezheti a javasolt változtatásokat, vagy dönthet úgy, hogy újraküldi az eredeti verziót.</span><span class="sxs-lookup"><span data-stu-id="c6160-144">He can make the requested changes first, or he can resubmit the original version.</span></span> <span data-ttu-id="c6160-145">Ha Balázs újraküldi a költségjelentést, a munkatétel-várólista egyik tagjának ellenőriznie kell a jelentést és a nyugtákat ismét.</span><span class="sxs-lookup"><span data-stu-id="c6160-145">If Sam resubmits the expense report, a member of the work item queue must review the expense report and the receipts again.</span></span>

### <a name="reassign"></a><span data-ttu-id="c6160-146">Ismételt hozzárendelés</span><span class="sxs-lookup"><span data-stu-id="c6160-146">Reassign</span></span>

<span data-ttu-id="c6160-147">A munkatétel-várólista tagjai átadhatják a várólistán szereplő dokumentumokat egy másik várólistának.</span><span class="sxs-lookup"><span data-stu-id="c6160-147">The members of a work item queue can reassign documents that are in that queue to another queue.</span></span> 

<span data-ttu-id="c6160-148">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja követi nyomon a várólistát.</span><span class="sxs-lookup"><span data-stu-id="c6160-148">For example, Julie, a member of the Adventure Works Expense Reports department, is monitoring the queue.</span></span> <span data-ttu-id="c6160-149">A munkaterhelés elosztásának érdekében Ágnes áthelyezheti a költségjelentést és a hozzá tartozó nyugtákat egy másik várólistához.</span><span class="sxs-lookup"><span data-stu-id="c6160-149">To help balance the workload, she can reassign the expense report, and the receipts that are included with it, to another queue.</span></span>

### <a name="release"></a><span data-ttu-id="c6160-150">Kiadás</span><span class="sxs-lookup"><span data-stu-id="c6160-150">Release</span></span>

<span data-ttu-id="c6160-151">Néha előfordul, hogy egy munkatétel-várólista tagja elfogad egy feladatot, majd később úgy dönt, hogy nem tudja befejezni azt.</span><span class="sxs-lookup"><span data-stu-id="c6160-151">Occasionally, a member of a work item queue might accept a task, but then decide that he or she can't complete the task.</span></span> <span data-ttu-id="c6160-152">Ebben az esetben az a személy, aki elfogadta a feladatot, kiadhatja a dokumentumot, vissza a munkatétel-várólistára.</span><span class="sxs-lookup"><span data-stu-id="c6160-152">In this case, the person who accepted the task can release the document back to the work item queue.</span></span> 

<span data-ttu-id="c6160-153">Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit.</span><span class="sxs-lookup"><span data-stu-id="c6160-153">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="c6160-154">Ha Ágnes úgy dönt, hogy nem tudja végrehajtani a feladatot, kiadhatja a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="c6160-154">If Julie decides that she can't complete the task, she can release the document.</span></span> <span data-ttu-id="c6160-155">A költségjelentés visszakerül a várólistára, így a Kalandorbolt költségjelentési részlegének további tagjai elvégezhetik a feladatot.</span><span class="sxs-lookup"><span data-stu-id="c6160-155">The expense report is returned to the queue, so that other members of the Adventure Works Expense Reports department can complete the task.</span></span>

## <a name="actions-that-a-decision-maker-can-perform"></a><span data-ttu-id="c6160-156">A feladat döntéshozója által végrehajtható műveletek</span><span class="sxs-lookup"><span data-stu-id="c6160-156">Actions that a decision maker can perform</span></span>
<span data-ttu-id="c6160-157">Általában egy dokumentum van a döntéshozóhoz rendelve, mert van egy kérdés, amit a döntéshozónak meg kell válaszolni.</span><span class="sxs-lookup"><span data-stu-id="c6160-157">Typically, a document is assigned to a decision maker, because there is a question that the decision maker must answer.</span></span> <span data-ttu-id="c6160-158">A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**.</span><span class="sxs-lookup"><span data-stu-id="c6160-158">The answer to the question is typically **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="c6160-159">Ha a döntés készítője nem választja ki az egyik választ, delegálhatja a döntést.</span><span class="sxs-lookup"><span data-stu-id="c6160-159">If the decision maker doesn't select one of those choices, he or she can delegate the decision.</span></span>

### <a name="choice-1-or-choice-2"></a><span data-ttu-id="c6160-160">\[1. lehetőség\] vagy \[. lehetőség\]</span><span class="sxs-lookup"><span data-stu-id="c6160-160">\[Choice 1\] or \[Choice 2\]</span></span>

<span data-ttu-id="c6160-161">A döntéshozónak választ kell adnia egy, a dokumentumot érintő kérdésre.</span><span class="sxs-lookup"><span data-stu-id="c6160-161">A decision maker must answer a question that is related to the document.</span></span> <span data-ttu-id="c6160-162">A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**.</span><span class="sxs-lookup"><span data-stu-id="c6160-162">The answer to the question is typically **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="c6160-163">A döntéshozó válasza fogja eldönteni, hogy a dokumentum feldolgozása melyik munkafolyamat-ágon fog elindulni.</span><span class="sxs-lookup"><span data-stu-id="c6160-163">The answer that the decision maker selects determines the workflow branch that is used to process the document.</span></span> 

<span data-ttu-id="c6160-164">Például, Balázs költségjelentése Jánoshoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-164">For example, Sam's expense report is assigned to John.</span></span> <span data-ttu-id="c6160-165">Jánosnak el kell döntenie, hogy a dokumentumban található információ miatt felhívja-e Balázs menedzserét.</span><span class="sxs-lookup"><span data-stu-id="c6160-165">John must decide whether the information in the document requires a call to Sam's manager.</span></span> <span data-ttu-id="c6160-166">Ha János úgy dönt, hogy szükséges a hívás, a költségjelentés Ilonához lesz rendelve, akinek fel kell hívnia Balázs menedzserét.</span><span class="sxs-lookup"><span data-stu-id="c6160-166">If John decides that a call is required, the expense report is assigned to Aretha, who must then call Sam's manager.</span></span> <span data-ttu-id="c6160-167">Ha János úgy dönt, hogy nem szükséges a hívás, a költségjelentés Ferenchez lesz rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="c6160-167">If John decides that a call isn't required, the expense report is assigned to Frank for approval.</span></span>

### <a name="delegate"></a><span data-ttu-id="c6160-168">Delegált</span><span class="sxs-lookup"><span data-stu-id="c6160-168">Delegate</span></span>

<span data-ttu-id="c6160-169">Mikor a döntéshozó delegálja a döntést, a dokumentum egy másik felhasználóhoz lesz rendelve, akinek meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="c6160-169">When a decision maker delegates a decision, the document is assigned to another user who must make the decision.</span></span> 

<span data-ttu-id="c6160-170">Például, Balázs költségjelentése Jánoshoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-170">For example, Sam's expense report is assigned to John.</span></span> <span data-ttu-id="c6160-171">János Máriához, az asszisztenséhez delegálja a döntést.</span><span class="sxs-lookup"><span data-stu-id="c6160-171">John delegates the decision to Maria, who is his assistant.</span></span> 

<span data-ttu-id="c6160-172">Mária ezután János nevében jár el.</span><span class="sxs-lookup"><span data-stu-id="c6160-172">Maria then acts on behalf of John.</span></span> <span data-ttu-id="c6160-173">Ha Mária úgy dönt, hogy szükséges a hívás, a költségjelentés Ilonához lesz rendelve, akinek fel kell hívnia Balázs menedzserét.</span><span class="sxs-lookup"><span data-stu-id="c6160-173">If Maria decides that a call to Sam's manager is required, the expense report is assigned to Aretha, who must then call Sam's manager.</span></span> <span data-ttu-id="c6160-174">Ha Mária úgy dönt, hogy nem szükséges a hívás, a költségjelentés Ferenchez lesz rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="c6160-174">If Maria decides that a call isn't required, the expense report is assigned to Frank for approval.</span></span>

## <a name="actions-that-an-approver-can-perform"></a><span data-ttu-id="c6160-175">A jóváhagyó által végrehajtható műveletek</span><span class="sxs-lookup"><span data-stu-id="c6160-175">Actions that an approver can perform</span></span>
<span data-ttu-id="c6160-176">Amikor a dokumentum a jóváhagyóhoz jut, a jóváhagyó a következő műveletek valamelyikét végezheti el: jóváhagyás, visszautasítás, delegálás vagy változtatás kérése.</span><span class="sxs-lookup"><span data-stu-id="c6160-176">When a document is assigned to an approver, the approver can perform one of the following actions: approve, reject, delegate, or request change.</span></span>

### <a name="approve"></a><span data-ttu-id="c6160-177">Jóváhagyás</span><span class="sxs-lookup"><span data-stu-id="c6160-177">Approve</span></span>

<span data-ttu-id="c6160-178">Amikor a jóváhagyó jóváhagyja a dokumentumot, a rendszer szükség esetén a munkafolyamat következő felhasználójához rendeli hozzá azt.</span><span class="sxs-lookup"><span data-stu-id="c6160-178">When an approver approves a document, the document is assigned to the next user in the workflow, if there is a next user.</span></span> <span data-ttu-id="c6160-179">Amennyiben nincs szükség további feldolgozásra, a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="c6160-179">If no additional processing is required, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-180">Például, Balázs elküldött egy 6000 USD dollárról szóló költségjelentést, és a dokumentum Ferenchez lett rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-180">For example, Sam has submitted an expense report for USD 6,000, and this document is assigned to Frank.</span></span> <span data-ttu-id="c6160-181">Ha Ferenc jóváhagyja a dokumentumot, akkor az Zsuzsannához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="c6160-181">When Frank approves the document, it's assigned to Sue for approval.</span></span> <span data-ttu-id="c6160-182">Miután Zsuzsanna jóváhagyja a költségjelentést, a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="c6160-182">When Sue approves the expense report, the workflow process ends.</span></span>

### <a name="reject"></a><span data-ttu-id="c6160-183">Elutasítás</span><span class="sxs-lookup"><span data-stu-id="c6160-183">Reject</span></span>

<span data-ttu-id="c6160-184">Amikor a jóváhagyó elutasítja a dokumentumot, a munkafolyamat véget ér.</span><span class="sxs-lookup"><span data-stu-id="c6160-184">When an approver rejects a document, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-185">Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Zsuzsannához lett rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-185">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Sue.</span></span> <span data-ttu-id="c6160-186">Ha Zsuzsanna visszautasítja a költségjelentést, a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="c6160-186">If Sue rejects the expense report, the workflow process ends.</span></span> 

<span data-ttu-id="c6160-187">Balázs ezután újraküldheti a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c6160-187">Sam can resubmit the expense report.</span></span> <span data-ttu-id="c6160-188">Elvégezhet változtatásokat, vagy újraküldheti a költségjelentés eredeti verzióját.</span><span class="sxs-lookup"><span data-stu-id="c6160-188">He can make changes first, or he can resubmit the original version of the expense report.</span></span> <span data-ttu-id="c6160-189">Ha Balázs újraküldi a költségjelentést, akkor a munkafolyamat újrakezdődik a jóváhagyási fázistól.</span><span class="sxs-lookup"><span data-stu-id="c6160-189">If Sam resubmits the expense report, the workflow process starts at the approval process.</span></span>

### <a name="delegate"></a><span data-ttu-id="c6160-190">Delegált</span><span class="sxs-lookup"><span data-stu-id="c6160-190">Delegate</span></span>

<span data-ttu-id="c6160-191">Amikor a jóváhagyó feladatot delegál, másik felhasználóhoz rendeli hozzá a dokumentumot jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="c6160-191">When an approver delegates a document, the document is assigned to another user for approval.</span></span> 

<span data-ttu-id="c6160-192">Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Ferenchez lett rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-192">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Frank.</span></span> <span data-ttu-id="c6160-193">Ferenc delegálja a költségjelentést Annának.</span><span class="sxs-lookup"><span data-stu-id="c6160-193">Frank delegates the expense report to Ann.</span></span> 

<span data-ttu-id="c6160-194">Anna ekkor Ferenc nevében jár el.</span><span class="sxs-lookup"><span data-stu-id="c6160-194">Ann then acts on behalf of Frank.</span></span> <span data-ttu-id="c6160-195">Ez azt jelenti, hogy miután Anna jóváhagyta a dokumentumot, az ugyanúgy Zsuzsannához kerül jóváhagyásra, mintha Ferenc hagyta volna jóvá.</span><span class="sxs-lookup"><span data-stu-id="c6160-195">Therefore, when Ann approves the document, it's assigned to Sue for approval, just as if Frank had approved it.</span></span> <span data-ttu-id="c6160-196">Miután Zsuzsanna jóváhagyta, a dokumentum Annához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="c6160-196">After Sue approves the document, it's sent to Ann for approval.</span></span>

### <a name="request-change"></a><span data-ttu-id="c6160-197">Változtatás kérése</span><span class="sxs-lookup"><span data-stu-id="c6160-197">Request change</span></span>

<span data-ttu-id="c6160-198">Amikor a jóváhagyó a dokumentum változtatását kéri, a dokumentumot visszaküldi a rendszer a létrehozónak.</span><span class="sxs-lookup"><span data-stu-id="c6160-198">When an approver requests a change to a document, the document is sent back to the originator.</span></span> 

<span data-ttu-id="c6160-199">Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Zsuzsannához lett rendelve.</span><span class="sxs-lookup"><span data-stu-id="c6160-199">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Sue.</span></span> <span data-ttu-id="c6160-200">Ha Zsuzsanna változtatást kér, akkor költségjelentés visszakerül Balázshoz.</span><span class="sxs-lookup"><span data-stu-id="c6160-200">If Sue requests a change, the expense report is sent back to Sam.</span></span> 

<span data-ttu-id="c6160-201">Balázs ezután újraküldheti a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c6160-201">Sam can resubmit the expense report.</span></span> <span data-ttu-id="c6160-202">Elvégezheti a javasolt változtatásokat, vagy újraküldheti a költségjelentés eredeti verzióját.</span><span class="sxs-lookup"><span data-stu-id="c6160-202">He can make the requested changes first, or he can resubmit the original version of the expense report.</span></span> <span data-ttu-id="c6160-203">Ha Balázs visszaküldi a költségjelentést, akkor az Ferenchez kerül vissza jóváhagyásra, ugyanis Ferenc a jóváhagyás folyamatának első jóváhagyója.</span><span class="sxs-lookup"><span data-stu-id="c6160-203">If Sam resubmits the expense report, it's sent to Frank for approval, because Frank is the first approver in the approval process.</span></span>



