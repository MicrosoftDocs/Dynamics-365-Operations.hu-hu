---
title: Alaptervezés futtatásának megfigyelése
description: A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845113"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="98618-103">Alaptervezés futtatásának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="98618-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98618-104">A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="98618-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="98618-105">Az USMF bemutatócég segítségével végezze el ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="98618-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="98618-106">Alaptervezés futtatása</span><span class="sxs-lookup"><span data-stu-id="98618-106">Run master planning</span></span>
1. <span data-ttu-id="98618-107">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="98618-107">Click Master planning.</span></span>
    * <span data-ttu-id="98618-108">Ezt az alapértelmezett irányítópulton fogja megtalálni.</span><span class="sxs-lookup"><span data-stu-id="98618-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="98618-109">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98618-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="98618-110">Példa: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="98618-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="98618-111">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="98618-111">Click Run.</span></span>
4. <span data-ttu-id="98618-112">Válassza az Igen lehetőséget a Követés feldolgozási ideje mezőben.</span><span class="sxs-lookup"><span data-stu-id="98618-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="98618-113">Ha a mező már be van jelölve, hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="98618-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="98618-114">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="98618-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="98618-115">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="98618-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="98618-116">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="98618-116">Click Filter.</span></span>
8. <span data-ttu-id="98618-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="98618-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="98618-118">Jelölje be a sort, ahol Mező = Cikk száma.</span><span class="sxs-lookup"><span data-stu-id="98618-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="98618-119">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98618-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="98618-120">Példa: T0001</span><span class="sxs-lookup"><span data-stu-id="98618-120">Example: T0001</span></span>  
10. <span data-ttu-id="98618-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="98618-121">Click OK.</span></span>
11. <span data-ttu-id="98618-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="98618-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="98618-123">Az Alaptervezés futtatásának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="98618-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="98618-124">Kattintson az előzmények lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98618-124">Click History.</span></span>
2. <span data-ttu-id="98618-125">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="98618-125">Click Inquiries.</span></span>
3. <span data-ttu-id="98618-126">Kattintson a Folyamatbeli tevékenység időtartama lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98618-126">Click Process task duration.</span></span>
4. <span data-ttu-id="98618-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="98618-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="98618-128">Minden egyes cikkre vonatkozóan áttekintést kaphat arról, hogy mennyi ideig tart az egyes tervezési lépések elvégzése.</span><span class="sxs-lookup"><span data-stu-id="98618-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

