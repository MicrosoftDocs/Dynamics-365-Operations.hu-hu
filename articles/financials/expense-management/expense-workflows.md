---
title: "Munkafolyamatok beállítása költségekhez"
description: "Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 19d725f15f00afce1a2ae4b336226f1dafa94b41
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="b18d4-103">Munkafolyamatok beállítása költségekhez</span><span class="sxs-lookup"><span data-stu-id="b18d4-103">Set up workflows for expense</span></span>

[!include[banner](../includes/banner.md)]<span data-ttu-id="b18d4-104"> Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait.</span><span class="sxs-lookup"><span data-stu-id="b18d4-104"> You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="b18d4-105">A dokumentumok, amelyekhez munkafolyamatokat lehet adni, többek között magukban foglalják a költségjelentéseket, az utazási igényléseket és a készpénzelőleg-igényléseket.</span><span class="sxs-lookup"><span data-stu-id="b18d4-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="b18d4-106">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="b18d4-106">A workflow represents a business process.</span></span> <span data-ttu-id="b18d4-107">Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="b18d4-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="b18d4-108">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="b18d4-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="b18d4-109">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét.</span><span class="sxs-lookup"><span data-stu-id="b18d4-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="b18d4-110">A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="b18d4-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="b18d4-111">A folyamat láthatósága – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="b18d4-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="b18d4-112">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="b18d4-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="b18d4-113">Központi munkalista – A felhasználók megjeleníthetik a centralizált munkalistát, amelyben megnézhetik a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.</span><span class="sxs-lookup"><span data-stu-id="b18d4-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="b18d4-114">**A létrehozható munkafolyamat-típusok**</span><span class="sxs-lookup"><span data-stu-id="b18d4-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="b18d4-115">Az alábbi táblázatban a **Költség** modulban létrehozható munkafolyamatok típusai szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="b18d4-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>

| <span data-ttu-id="b18d4-116">**Típus**</span><span class="sxs-lookup"><span data-stu-id="b18d4-116">**Type**</span></span>                           | <span data-ttu-id="b18d4-117">**Típus**</span><span class="sxs-lookup"><span data-stu-id="b18d4-117">**Use this type to**</span></span>                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| <span data-ttu-id="b18d4-118">**Költségjelentés**</span><span class="sxs-lookup"><span data-stu-id="b18d4-118">**Expense report**</span></span>                 | <span data-ttu-id="b18d4-119">Jóváhagyási munkafolyamatok létrehozása a költségjelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="b18d4-119">Create approval workflows for expense reports.</span></span>                       |      
| <span data-ttu-id="b18d4-120">**Költségjelentés automatikus feladása**</span><span class="sxs-lookup"><span data-stu-id="b18d4-120">**Expense report auto posting**</span></span>    | <span data-ttu-id="b18d4-121">Hozzon létre automatikus dokumentumfeladási munkafolyamatokat a költségjelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="b18d4-121">Create automatic posting workflows for expense reports.</span></span>              |     
| <span data-ttu-id="b18d4-122">**Költségsortétel**</span><span class="sxs-lookup"><span data-stu-id="b18d4-122">**Expense line item**</span></span>              | <span data-ttu-id="b18d4-123">Jóváhagyási munkafolyamatok létrehozása a költségjelentések sortételeihez.</span><span class="sxs-lookup"><span data-stu-id="b18d4-123">Create approval workflows for line items on expense reports.</span></span>         |     
| <span data-ttu-id="b18d4-124">**Költségsortétel automatikus feladása**</span><span class="sxs-lookup"><span data-stu-id="b18d4-124">**Expense line item auto posting**</span></span> | <span data-ttu-id="b18d4-125">Automatikus feladási munkafolyamatok létrehozása a költségjelentések sortételeihez.</span><span class="sxs-lookup"><span data-stu-id="b18d4-125">Create automatic posting workflows for line items on expense reports.</span></span>|
| <span data-ttu-id="b18d4-126">**Utazási igénylés**</span><span class="sxs-lookup"><span data-stu-id="b18d4-126">**Travel requisition**</span></span>             | <span data-ttu-id="b18d4-127">Jóváhagyási munkafolyamatok létrehozása az utazási igénylésekhez.</span><span class="sxs-lookup"><span data-stu-id="b18d4-127">Create approval workflows for travel requisitions.</span></span>                   |    
| <span data-ttu-id="b18d4-128">**Készpénzelőleg-igénylés**</span><span class="sxs-lookup"><span data-stu-id="b18d4-128">**Cash advance request**</span></span>           | <span data-ttu-id="b18d4-129">Hozza létre a készpénzelőleg-igénylések jóváhagyási munkafolyamatait.</span><span class="sxs-lookup"><span data-stu-id="b18d4-129">Create approval workflows for cash advance requests.</span></span>                 |     
| <span data-ttu-id="b18d4-130">**Áfa-visszaigénylés**</span><span class="sxs-lookup"><span data-stu-id="b18d4-130">**VAT tax recovery**</span></span>               | <span data-ttu-id="b18d4-131">Hozzon létre munkafolyamatokat az áfa-visszaigénylések jóváhagyására.</span><span class="sxs-lookup"><span data-stu-id="b18d4-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span> |       

