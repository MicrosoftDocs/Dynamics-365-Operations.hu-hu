---
title: "Költségjelentés feladása"
description: "Ez a témakör bemutatja, hogyan lehet a költségjelentéseket a főkönyvbe feladni."
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: cc3aae061038202ec4f314654d9149c31e2575bb
ms.contentlocale: hu-hu
ms.lasthandoff: 03/13/2018

---

# <a name="post-an-expense-report"></a><span data-ttu-id="2b26a-103">Költségjelentés feladása</span><span class="sxs-lookup"><span data-stu-id="2b26a-103">Post an expense report</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2b26a-104">A költségjelentés jóváhagyás és a főkönyvbe történő átvitel után feladható a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="2b26a-104">After an expense report has been approved and transferred to the general journal, it can be posted to the general ledger.</span></span> <span data-ttu-id="2b26a-105">Költségjelentés feladásakor az általános forgalmi adó (áfa) visszatérítésére jogosult költségeket a rendszer azonosítja.</span><span class="sxs-lookup"><span data-stu-id="2b26a-105">When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified.</span></span> <span data-ttu-id="2b26a-106">Az áfa-befizetések ellenőrzésének és visszaigénylésének feladata a költségjelentés ellenőrzéséért felelős alkalmazotthoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="2b26a-106">The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.</span></span>

<span data-ttu-id="2b26a-107">Ha a költségjelentésben szereplő költségeket egy olyan vállalatra terhelik, amelyik nem az alkalmazottat alkalmazó vállalat, ellenőriznie kell azt a vállalatot, amelynek ezek a költségek fizetendők, és a vállalatot, amelytől a költségeket követelik.</span><span class="sxs-lookup"><span data-stu-id="2b26a-107">If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify the company that those expenses are owed to and the company that the expenses are owed from.</span></span> <span data-ttu-id="2b26a-108">Például az alkalmazott, aki elküldte a költségjelentést, a DAT vállalatnál dolgozik, de a DIR vállalatnak számolt el egy költséget.</span><span class="sxs-lookup"><span data-stu-id="2b26a-108">For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company.</span></span> <span data-ttu-id="2b26a-109">Ebben az esetben a DAT a vállalat, amelynek a költség fizetendő, és a DIR a vállalat, amelytől a költséget követelik.</span><span class="sxs-lookup"><span data-stu-id="2b26a-109">In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from.</span></span> <span data-ttu-id="2b26a-110">Miután ellenőrizte a naplósorokat, feladhatja a főkönyvbe a költségsorokat.</span><span class="sxs-lookup"><span data-stu-id="2b26a-110">After you verify these journal lines, you can post the expense lines to the general ledger.</span></span>

<span data-ttu-id="2b26a-111">A költségjelentések feladásához a **Jóváhagyott költségjelentések** oldalon válassza ki a költségjelentést, majd ezután a műveleti ablakban válassza a **Feladás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b26a-111">To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.</span></span>

<span data-ttu-id="2b26a-112">A listában szereplő költségjelentések egy időben is feladhatók.</span><span class="sxs-lookup"><span data-stu-id="2b26a-112">You can also post all the expense reports in the list at the same time.</span></span> <span data-ttu-id="2b26a-113">Válassza ki az összes költségjelentést, majd ezután válassza a **Feladás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b26a-113">Select all the expense reports, and then select **Post**.</span></span>

