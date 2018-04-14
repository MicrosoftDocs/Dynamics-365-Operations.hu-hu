---
title: "Költségjelentések és több jóváhagyó"
description: "Ez a témakör az egynél több személy jóváhagyását igénylő költségjelentésekkel kapcsolatban tartalmaz tájékoztatást."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7cd2e56dab48ad8f2380dcaa72e3317250b5b2f0
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="c0581-103">Költségjelentések és több jóváhagyó</span><span class="sxs-lookup"><span data-stu-id="c0581-103">Expense reports and multiple approvers</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="c0581-104">A szervezet költségjóváhagyási szabályaitól függően elképzelhető, hogy több mint egy személynek kell jóváhagynia egy adott alkalmazott által benyújtott költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c0581-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="c0581-105">A költségjelentés jóváhagyási munkafolyamatának beállításakor olyan munkafolyamat-elemeket adhat meg, amelyek feladatokat vagy lépéseket tartalmaznak egy vagy több költségjelentés-jóváhagyó számára.</span><span class="sxs-lookup"><span data-stu-id="c0581-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="c0581-106">Például előfordulhat, hogy minden költségjelentést először jóvá kell hagynia először a jelentést elküldő alkalmazott vezetőjének, majd a kötelezettségek koordinátorának.</span><span class="sxs-lookup"><span data-stu-id="c0581-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="c0581-107">Ha úgy dönt, hogy több költségjelentés-jóváhagyó szükséges, a munkafolyamat-elemeket a következő módok bármelyikével hozzáadhatja:</span><span class="sxs-lookup"><span data-stu-id="c0581-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="c0581-108">Egy jóváhagyási elem hozzáadása, amelynek egy lépése van.</span><span class="sxs-lookup"><span data-stu-id="c0581-108">Add one approval element that has one step.</span></span> <span data-ttu-id="c0581-109">Előfordulhat például, hogy lépés azt követelik meg, hogy a költségjelentés egy felhasználócsoporthoz legyen hozzárendelve, és ezután jóvá kell hagynia a felhasználói csoport tagjainak 50 százalékának.</span><span class="sxs-lookup"><span data-stu-id="c0581-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="c0581-110">Egy jóváhagyási elem hozzáadása, amelynek több lépése van.</span><span class="sxs-lookup"><span data-stu-id="c0581-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="c0581-111">Például a jóváhagyási elemnek a következő lépésekei lehetnek:</span><span class="sxs-lookup"><span data-stu-id="c0581-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="c0581-112">A költségjelentést elküldő alkalmazott felettese jóváhagyja a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c0581-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="c0581-113">A Kötelezettségkezelő adminisztrátor ellenőrzi a nyugtákat és a költségjelentés elemeit.</span><span class="sxs-lookup"><span data-stu-id="c0581-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="c0581-114">A költségvetésjóváhagyó jóváhagyja a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c0581-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="c0581-115">Több jóváhagyási elem hozzáadása, amelyek mindegyikének egy lépése van.</span><span class="sxs-lookup"><span data-stu-id="c0581-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="c0581-116">Például különálló jóváhagyási elem hozzáadása az alábbi lépések mindegyikéhez:</span><span class="sxs-lookup"><span data-stu-id="c0581-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="c0581-117">Az alkalmazott felettese jóváhagyja a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c0581-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="c0581-118">A költségvetésjóváhagyó jóváhagyja a költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="c0581-118">The budget owner approves the expense report.</span></span>

