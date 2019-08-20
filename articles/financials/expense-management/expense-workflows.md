---
title: Munkafolyamatok beállítása költségekhez
description: Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840961"
---
# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="95363-103">Munkafolyamatok beállítása költségekhez</span><span class="sxs-lookup"><span data-stu-id="95363-103">Set up workflows for expense</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95363-104"> Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait.</span><span class="sxs-lookup"><span data-stu-id="95363-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="95363-105">A dokumentumok, amelyekhez munkafolyamatokat lehet adni, többek között magukban foglalják a költségjelentéseket, az utazási igényléseket és a készpénzelőleg-igényléseket.</span><span class="sxs-lookup"><span data-stu-id="95363-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="95363-106">A munkafolyamat egy üzleti folyamatot jelent.</span><span class="sxs-lookup"><span data-stu-id="95363-106">A workflow represents a business process.</span></span> <span data-ttu-id="95363-107">Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="95363-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="95363-108">A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="95363-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="95363-109">**Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét.</span><span class="sxs-lookup"><span data-stu-id="95363-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="95363-110">A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.</span><span class="sxs-lookup"><span data-stu-id="95363-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="95363-111">A folyamat láthatósága – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit.</span><span class="sxs-lookup"><span data-stu-id="95363-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="95363-112">Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.</span><span class="sxs-lookup"><span data-stu-id="95363-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="95363-113">Központi munkalista – A felhasználók megjeleníthetik a centralizált munkalistát, amelyben megnézhetik a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.</span><span class="sxs-lookup"><span data-stu-id="95363-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="95363-114">**A létrehozható munkafolyamat-típusok**</span><span class="sxs-lookup"><span data-stu-id="95363-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="95363-115">Az alábbi táblázatban a **Költség** modulban létrehozható munkafolyamatok típusai szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="95363-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="95363-116"><strong>Típus</strong></span><span class="sxs-lookup"><span data-stu-id="95363-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="95363-117"><strong>Típus</strong></span><span class="sxs-lookup"><span data-stu-id="95363-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="95363-118"><strong>Költségjelentés</strong></span><span class="sxs-lookup"><span data-stu-id="95363-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="95363-119">Jóváhagyási munkafolyamatok létrehozása a költségjelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="95363-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="95363-120"><strong>Költségjelentés automatikus feladása</strong></span><span class="sxs-lookup"><span data-stu-id="95363-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="95363-121">Hozzon létre automatikus dokumentumfeladási munkafolyamatokat a költségjelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="95363-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="95363-122"><strong>Költségsortétel</strong></span><span class="sxs-lookup"><span data-stu-id="95363-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="95363-123">Jóváhagyási munkafolyamatok létrehozása a költségjelentések sortételeihez.</span><span class="sxs-lookup"><span data-stu-id="95363-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="95363-124"><strong>Költségsortétel automatikus feladása</strong></span><span class="sxs-lookup"><span data-stu-id="95363-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="95363-125">Automatikus feladási munkafolyamatok létrehozása a költségjelentések sortételeihez.</span><span class="sxs-lookup"><span data-stu-id="95363-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="95363-126"><strong>Utazási igénylés</strong></span><span class="sxs-lookup"><span data-stu-id="95363-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="95363-127">Jóváhagyási munkafolyamatok létrehozása az utazási igénylésekhez.</span><span class="sxs-lookup"><span data-stu-id="95363-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="95363-128"><strong>Készpénzelőleg-igénylés</strong></span><span class="sxs-lookup"><span data-stu-id="95363-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="95363-129">Hozza létre a készpénzelőleg-igénylések jóváhagyási munkafolyamatait.</span><span class="sxs-lookup"><span data-stu-id="95363-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="95363-130"><strong>Áfa-visszaigénylés</strong></span><span class="sxs-lookup"><span data-stu-id="95363-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="95363-131">Hozzon létre munkafolyamatokat az áfa-visszaigénylések jóváhagyására.</span><span class="sxs-lookup"><span data-stu-id="95363-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

