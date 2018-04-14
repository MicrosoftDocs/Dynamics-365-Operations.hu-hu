---
title: "A főkönyv lezárása időszak végén"
description: "A témakör a főkönyvi időszak zárásának végrehajtásakor általában elvégzett feladatokat ismerteti."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c08d039863253b33438c92243d5c164408ef85f3
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="60f26-103">A főkönyv lezárása időszak végén</span><span class="sxs-lookup"><span data-stu-id="60f26-103">Close the general ledger at period end</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="60f26-104">A témakör a főkönyvi időszak zárásának végrehajtásakor általában elvégzett feladatokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="60f26-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="60f26-105">A Főkönyvben, záró eljárásokat az időszak vagy az év végén hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="60f26-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="60f26-106">A záró folyamatok előkészítik a rendszert egy új időszakra.</span><span class="sxs-lookup"><span data-stu-id="60f26-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="60f26-107">A rendszer új évre történő felkészítéséhez futtatni kell az év végi zárás folyamatot.</span><span class="sxs-lookup"><span data-stu-id="60f26-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="60f26-108">Minden szervezetnek különböző folyamatai és lépései vannak, amelyek az időszakok végén futnak le.</span><span class="sxs-lookup"><span data-stu-id="60f26-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="60f26-109">Néhány a lehetséges időszakvégi lépések közül:</span><span class="sxs-lookup"><span data-stu-id="60f26-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="60f26-110">Fejezzen be minden feladatot minden más modulhoz, például Kinnlevőségek, Kötelezettségek, és Készlet.</span><span class="sxs-lookup"><span data-stu-id="60f26-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="60f26-111">Győződjön meg róla, hogy az összes napló feladása került.</span><span class="sxs-lookup"><span data-stu-id="60f26-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="60f26-112">Futtasson devizaátértékelést, hogy létrehozzon minden nem realizált nyereséget vagy elvesztett összeget.</span><span class="sxs-lookup"><span data-stu-id="60f26-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="60f26-113">Kiegyenlítési tranzakciók a főkönyvi számlák között.</span><span class="sxs-lookup"><span data-stu-id="60f26-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="60f26-114">Felosztási kérések feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="60f26-114">Process any required allocations.</span></span>
-   <span data-ttu-id="60f26-115">Manuális helyesbítések időszak végén.</span><span class="sxs-lookup"><span data-stu-id="60f26-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="60f26-116">Tranzakciók naplózása, és a **Főkönyvi napló** jelentés felülvizsgálata.</span><span class="sxs-lookup"><span data-stu-id="60f26-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="60f26-117">Egy konszolidációs vállalat vagy Pénzügyi jelentések segítségével konszolidáció végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="60f26-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="60f26-118">Időszak végi pénzügyi kimutatások létrehozása a Pénzügyi jelentések segítségével.</span><span class="sxs-lookup"><span data-stu-id="60f26-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="60f26-119">Főkönyvi időszak átállítása **Várakoztatott** állapotra, így további feladás nem történik.</span><span class="sxs-lookup"><span data-stu-id="60f26-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="60f26-120">Időszakot korlátozhat egy megadott felhasználócsoportnak, amikor az időszakvégi tevékenységek megjelennek, a jobb ellenőrzés érdekében.</span><span class="sxs-lookup"><span data-stu-id="60f26-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="60f26-121">Nem tanácsos időszakokat **Véglegesen lezárva** állapotba helyezni, mert egy lezárt időszakot nem lehet újranyitni.</span><span class="sxs-lookup"><span data-stu-id="60f26-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="60f26-122">A Pénzügyi időszak lezárása munkaterület használható a különböző időszakzáró folyamatok megszervezéséhez és nyomon követéséhez.</span><span class="sxs-lookup"><span data-stu-id="60f26-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="60f26-123">A képernyővel kapcsolatos további információkat lásd a következő témakörökben:</span><span class="sxs-lookup"><span data-stu-id="60f26-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="60f26-124">Pénzügyi időszak lezárása munkaterület</span><span class="sxs-lookup"><span data-stu-id="60f26-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="60f26-125">Év végi zárás</span><span class="sxs-lookup"><span data-stu-id="60f26-125">Year end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="60f26-126">Pénzügyi időszakok tömeges lezárása</span><span class="sxs-lookup"><span data-stu-id="60f26-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)





