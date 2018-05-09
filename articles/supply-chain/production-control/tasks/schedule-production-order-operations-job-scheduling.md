--- 
title: "Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése"
description: "Ez az eljárás a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezésére összpontosít."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 690a0d2db67bc7a13adf186e3e9c3b9238932eb0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="95ac5-103">Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="95ac5-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="95ac5-104">Ez az eljárás a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezésére összpontosít.</span><span class="sxs-lookup"><span data-stu-id="95ac5-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="95ac5-105">Nem jön létre feladat műveletütemezéssel ugyanakkor feladatütemezéssel létrehozhatók feladatok.</span><span class="sxs-lookup"><span data-stu-id="95ac5-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="95ac5-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="95ac5-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="95ac5-107">Ez az eljárás az elkülönített gyártási környezetben dolgozó termelésvezető, gyártástervező vagy az üzemirányítási felügyelő munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="95ac5-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="95ac5-108">Termelési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="95ac5-108">Create a production order</span></span>
1. <span data-ttu-id="95ac5-109">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="95ac5-110">Kattintson az Új termelési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-110">Click New production order.</span></span>
3. <span data-ttu-id="95ac5-111">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95ac5-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="95ac5-112">Válassza ki a D0001 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="95ac5-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="95ac5-113">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="95ac5-114">Termelési rendelés műveleteinek ütemezése</span><span class="sxs-lookup"><span data-stu-id="95ac5-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="95ac5-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="95ac5-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="95ac5-116">Jelölje ki az imént létrehozott termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="95ac5-116">Select the production order that you have just created.</span></span> <span data-ttu-id="95ac5-117">A lista tetején kell lennie.</span><span class="sxs-lookup"><span data-stu-id="95ac5-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="95ac5-118">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="95ac5-119">Kattintson a Műveletek ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="95ac5-120">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előre” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95ac5-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="95ac5-121">Adjon meg egy dátumot az Ütemezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="95ac5-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="95ac5-122">Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet.</span><span class="sxs-lookup"><span data-stu-id="95ac5-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="95ac5-123">Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.</span><span class="sxs-lookup"><span data-stu-id="95ac5-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="95ac5-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="95ac5-124">Click OK.</span></span>
7. <span data-ttu-id="95ac5-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="95ac5-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="95ac5-126">Ügyeljen rá, hogy a termelés állapota az Ütemezve értékre változik.</span><span class="sxs-lookup"><span data-stu-id="95ac5-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="95ac5-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95ac5-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="95ac5-128">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-128">Click All jobs.</span></span>
    * <span data-ttu-id="95ac5-129">Vegye figyelembe, hogy műveletütemezéssel nem hozható létre feladat.</span><span class="sxs-lookup"><span data-stu-id="95ac5-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="95ac5-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="95ac5-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="95ac5-131">Termelési rendelés feladatainak ütemezése</span><span class="sxs-lookup"><span data-stu-id="95ac5-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="95ac5-132">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="95ac5-133">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="95ac5-134">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előre” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95ac5-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="95ac5-135">Adjon meg egy dátumot az Ütemezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="95ac5-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="95ac5-136">Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet.</span><span class="sxs-lookup"><span data-stu-id="95ac5-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="95ac5-137">Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.</span><span class="sxs-lookup"><span data-stu-id="95ac5-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="95ac5-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="95ac5-138">Click OK.</span></span>
6. <span data-ttu-id="95ac5-139">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="95ac5-140">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-140">Click All jobs.</span></span>
    * <span data-ttu-id="95ac5-141">Vegye figyelembe, hogy az aktív útvonal alapján a feladatütemezéssel 5 feladat jött létre.</span><span class="sxs-lookup"><span data-stu-id="95ac5-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  


