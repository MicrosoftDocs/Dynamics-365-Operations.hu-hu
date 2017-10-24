--- 
title: "Lean igénykövetés az értékelési rendelésekből"
description: "Ez az eljárás arra irányul, hogy ellenőrizze az igénykövetési fát egy olyan értékesítési sorból, ahol a cikk létrehozása kanbanokkal történik."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3aa8cd2c0be56875904158f041cf120c466d9e9a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="cc9a6-103">Lean igénykövetés az értékelési rendelésekből</span><span class="sxs-lookup"><span data-stu-id="cc9a6-103">Lean pegging from sales orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc9a6-104">Ez az eljárás arra irányul, hogy ellenőrizze az igénykövetési fát egy olyan értékesítési sorból, ahol a cikk létrehozása kanbanokkal történik.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="cc9a6-105">Az igénykövetési fa ellenőrzése után minden kanbanfeladat tervezetté válik.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="cc9a6-106">Ez olyan rendelési esetekben hasznos, ahol a rendelés végrehajtójának biztosítania kell a termelés azonnali elindítását.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="cc9a6-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cc9a6-108">Az eljárás a lean vállalatnak dolgozó haladó rendelésvégrehajtók számára ajánlott.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="cc9a6-109">Hozzon létre egy kanban által szabályozott cikkre vonatkozó értékesítési sort</span><span class="sxs-lookup"><span data-stu-id="cc9a6-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="cc9a6-110">Ugrás az összes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="cc9a6-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-111">Click New.</span></span>
3. <span data-ttu-id="cc9a6-112">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="cc9a6-113">Használja a következőt: US-001.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-113">Use US-001.</span></span>  
4. <span data-ttu-id="cc9a6-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-114">Click OK.</span></span>
5. <span data-ttu-id="cc9a6-115">A Cikkszám mezőbe írja be az „L0001” értéket.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="cc9a6-116">Állítsa a mennyiséget 30 értékre.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="cc9a6-117">Az esemény kanbanszabály elindítása miatt fontos, hogy a mennyiség 24-nél nagyobb legyen.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="cc9a6-118">Igénykövetési fa megnyitása</span><span class="sxs-lookup"><span data-stu-id="cc9a6-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="cc9a6-119">Kattintson a Termék és készlet menüpontra.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-119">Click Product and supply.</span></span>
2. <span data-ttu-id="cc9a6-120">Az igénykövetési fa megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="cc9a6-121">Figyelje meg, hogy az igénykövetési fa megjeleníti az értékesítési rendelési sorhoz szükséges igénykövetés minden szintjét.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="cc9a6-122">Ebben az esetben a kanbanoknak és minden szükséges összetevőnek két szintje van.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="cc9a6-123">Igénykövetési fa megtervezése</span><span class="sxs-lookup"><span data-stu-id="cc9a6-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="cc9a6-124">A fán válassza ki a következőt: „Értékesítési sor: 000832\Kanban: 000558”.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="cc9a6-125">Bontsa ki a Kanbanfeladatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="cc9a6-126">Figyelje meg, hogy a kanbanfeladat állapota Nem tervezett.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="cc9a6-127">Kattintson A teljes igénykövetési fa megtervezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="cc9a6-128">Ez megtervezi az igénykövetési fában szereplő összes kanbanfeladatot, amelynek során a Feladat állapota megváltozik: Nem tervezett helyett Tervezett lesz.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="cc9a6-129">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="cc9a6-129">Refresh the page.</span></span>
    * <span data-ttu-id="cc9a6-130">Figyelje meg, hogy a kanban Feladat állapota megváltozott: Nem tervezett helyett Tervezett lett.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="cc9a6-131">A fán válassza ki a következőt: „Értékesítési sor: 000832\Kanban: 000558\Kiadás: L0001\Kanban: 000559”.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="cc9a6-132">A második kanbanhoz tartozó feladat szintén tervezett, mivel az egész igénykövetési fa tervezett.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="cc9a6-133">Figyelje meg, hogy a kanbanfeladat állapota megváltozott: Nem tervezett helyett Tervezett lett.</span><span class="sxs-lookup"><span data-stu-id="cc9a6-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  

