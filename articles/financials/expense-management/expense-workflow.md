---
title: "A költségek munkafolyamata"
description: "Ez a témakör bemutatja, hogyan használhatja a Microsoft Dynamics 365 for Finance and Operations munkafolyamat-rendszerét a költségjelentések felülvizsgálati folyamatának beállítására a Költséggazdálkodás modulban."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6ee607f723659a5b6ecd655ba4fdfca35a4c582d
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="expense-workflow"></a><span data-ttu-id="e0adb-103">A költségek munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="e0adb-103">Expense workflow</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e0adb-104">A Microsoft Dynamics 365 for Finance and Operations munkafolyamat-rendszerét a költségjelentések felülvizsgálati folyamatának beállítására használhatja a Költséggazdálkodás modulban.</span><span class="sxs-lookup"><span data-stu-id="e0adb-104">You can use the workflow system in Microsoft Dynamics 365 for Finance and Operations, to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="e0adb-105">Olyan munkafolyamat adható meg, amely a következő feltételek használatával határozza meg, ki hagyja jóvá a költségjelentéseket:</span><span class="sxs-lookup"><span data-stu-id="e0adb-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="e0adb-106">Az alkalmazott jelentési hierarchiája, és az előre meghatározott jóváhagyási korlátok</span><span class="sxs-lookup"><span data-stu-id="e0adb-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="e0adb-107">Köztes jóváhagyókat és végleges jóváhagyót támogató többszintű jóváhagyás</span><span class="sxs-lookup"><span data-stu-id="e0adb-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="e0adb-108">Pénzügyi dimenziók és projektfelelősség</span><span class="sxs-lookup"><span data-stu-id="e0adb-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="e0adb-109">Hozzárendelés adott felhasználókhoz vagy felhasználói csoportokhoz</span><span class="sxs-lookup"><span data-stu-id="e0adb-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="e0adb-110">Munkafolyamat-jóváhagyásokat lehet létrehozni a költségjelentésekhez, az utazási igénylésekhez, a készpénzelőlegekhez és az általános forgalmi adó (áfa) visszaigényléséhez.</span><span class="sxs-lookup"><span data-stu-id="e0adb-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="e0adb-111">**példa**</span><span class="sxs-lookup"><span data-stu-id="e0adb-111">**Example**</span></span>

<span data-ttu-id="e0adb-112">A következő folyamat példaként illusztrálja a költségjelentésekre vonatkozó költségkezelési munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="e0adb-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="e0adb-113">Egy alkalmazott létrehoz és ment egy költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="e0adb-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="e0adb-114">Az alkalmazott benyújtja a költségjelentést jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="e0adb-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="e0adb-115">A munkafolyamat beállításakor meghatározott szabályok alapján a rendszer azonosítja a jóváhagyót.</span><span class="sxs-lookup"><span data-stu-id="e0adb-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="e0adb-116">A jóváhagyó értesítést kap a jóváhagyásra váró költségjelentésről.</span><span class="sxs-lookup"><span data-stu-id="e0adb-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="e0adb-117">A jóváhagyó ellenőrzi a költségjelentést, és ellenőrzi, hogy a következő feltételek teljesülnek:</span><span class="sxs-lookup"><span data-stu-id="e0adb-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="e0adb-118">A költségek nem sértik a költségszabályokat.</span><span class="sxs-lookup"><span data-stu-id="e0adb-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="e0adb-119">Ha egy költség megsért egy szabályt, a jóváhagyó ellenőrzi, hogy a költségjelentésben szerepel-e érvényes üzleti indoklás.</span><span class="sxs-lookup"><span data-stu-id="e0adb-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="e0adb-120">A költségjelentéshez csatolják az elektronikus nyugtákat.</span><span class="sxs-lookup"><span data-stu-id="e0adb-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="e0adb-121">A jóváhagyó jóváhagyja a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="e0adb-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="e0adb-122">A költségjelentést feladásra a kötelezettségek koordinátorához rendeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e0adb-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="e0adb-123">A következő lépések valamelyike történik, attól függően, hogy be van-e állítva az automatikus feladás:</span><span class="sxs-lookup"><span data-stu-id="e0adb-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="e0adb-124">Ha az automatikus feladás be van állítva, megtörténik a költségjelentés feldolgozása feladásra, és a költségjelentés állapota frissül.</span><span class="sxs-lookup"><span data-stu-id="e0adb-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="e0adb-125">Ha az automatikus feladás nincs konfigurálva, a kötelezettségek koordinátora ellenőrzi, hogy minden eredeti nyugtát benyújtottak-e, és hogy a nyugták megfelelnek-e a költségjelentés költségeinek.</span><span class="sxs-lookup"><span data-stu-id="e0adb-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="e0adb-126">A költségjelentésben megadott összes adókód helyességét is ellenőrizni kell.</span><span class="sxs-lookup"><span data-stu-id="e0adb-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="e0adb-127">A követelmények ellenőrzését követően megtörténik a költségjelentés feladása.</span><span class="sxs-lookup"><span data-stu-id="e0adb-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="e0adb-128">A költségjelentés feladása után megtörténik a fizetés engedélyzése a költségjelentéshez, és az alkalmazott számára megtörténik a költségei megtérítése.</span><span class="sxs-lookup"><span data-stu-id="e0adb-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>

