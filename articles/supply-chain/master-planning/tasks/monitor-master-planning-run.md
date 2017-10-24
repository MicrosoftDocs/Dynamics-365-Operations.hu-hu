--- 
title: "Alaptervezés futtatásának megfigyelése"
description: "A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="bb4ba-103">Alaptervezés futtatásának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="bb4ba-103">Monitor a master planning run</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bb4ba-104">A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="bb4ba-105">Az USMF bemutatócég segítségével végezze el ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="bb4ba-106">Alaptervezés futtatása</span><span class="sxs-lookup"><span data-stu-id="bb4ba-106">Run master planning</span></span>
1. <span data-ttu-id="bb4ba-107">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-107">Click Master planning.</span></span>
    * <span data-ttu-id="bb4ba-108">Ezt az alapértelmezett irányítópulton fogja megtalálni.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="bb4ba-109">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="bb4ba-110">Példa: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="bb4ba-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="bb4ba-111">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-111">Click Run.</span></span>
4. <span data-ttu-id="bb4ba-112">Válassza az Igen lehetőséget a Követés feldolgozási ideje mezőben.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="bb4ba-113">Ha a mező már be van jelölve, hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="bb4ba-114">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="bb4ba-115">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="bb4ba-116">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-116">Click Filter.</span></span>
8. <span data-ttu-id="bb4ba-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bb4ba-118">Jelölje be a sort, ahol Mező = Cikk száma.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="bb4ba-119">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="bb4ba-120">Példa: T0001</span><span class="sxs-lookup"><span data-stu-id="bb4ba-120">Example: T0001</span></span>  
10. <span data-ttu-id="bb4ba-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-121">Click OK.</span></span>
11. <span data-ttu-id="bb4ba-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="bb4ba-123">Az Alaptervezés futtatásának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="bb4ba-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="bb4ba-124">Kattintson az előzmények lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-124">Click History.</span></span>
2. <span data-ttu-id="bb4ba-125">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-125">Click Inquiries.</span></span>
3. <span data-ttu-id="bb4ba-126">Kattintson a Folyamatbeli tevékenység időtartama lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-126">Click Process task duration.</span></span>
4. <span data-ttu-id="bb4ba-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bb4ba-128">Minden egyes cikkre vonatkozóan áttekintést kaphat arról, hogy mennyi ideig tart az egyes tervezési lépések elvégzése.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


