---
title: Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése
description: Ez a témakör a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezését ismerteti.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bbb4da093cd8a0fc6cd85e1f93dfb91f0fb8a382
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981131"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="5a1f0-103">Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="5a1f0-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5a1f0-104">Ez a témakör a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezését ismerteti.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="5a1f0-105">Nem jön létre feladat műveletütemezéssel ugyanakkor feladatütemezéssel létrehozhatók feladatok.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="5a1f0-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="5a1f0-107">Ez az eljárás az elkülönített gyártási környezetben dolgozó termelésvezető, gyártástervező vagy az üzemirányítási felügyelő munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="5a1f0-108">Termelési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="5a1f0-108">Create a production order</span></span>
1. <span data-ttu-id="5a1f0-109">A navigációs ablaktáblán ugorj a **Modulok > Gyártásvezérlés > Termelési rendelések > Minden termelési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="5a1f0-110">Válassza ki az **Új termelési rendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-110">Select **New production order**.</span></span>
3. <span data-ttu-id="5a1f0-111">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="5a1f0-112">Válassza ki a **D0001** cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="5a1f0-113">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="5a1f0-114">Termelési rendelés műveleteinek ütemezése</span><span class="sxs-lookup"><span data-stu-id="5a1f0-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="5a1f0-115">Jelölje meg az újonnan létrehozott sort.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="5a1f0-116">A műveleti ablaktáblán válassza ki az **Ütemezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="5a1f0-117">Válassza ki a **Műveletek ütemezése lehetőséget**.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="5a1f0-118">Az **Ütemezés iránya** mezőben válassza ki a **Szállítási dátumtól előre** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="5a1f0-119">Adjon meg egy dátumot az **Ütemezési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="5a1f0-120">Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="5a1f0-121">Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="5a1f0-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-122">Select **OK**.</span></span>
7. <span data-ttu-id="5a1f0-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-123">In the list, mark the selected row.</span></span> <span data-ttu-id="5a1f0-124">Ügyeljen rá, hogy a termelés állapota az **Ütemezve** értékre változik.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="5a1f0-125">Válassza ki a **Minden feladat** elemet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-125">Select **All jobs**.</span></span> <span data-ttu-id="5a1f0-126">Vegye figyelembe, hogy műveletütemezéssel nem hozható létre feladat.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="5a1f0-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="5a1f0-128">Termelési rendelés feladatainak ütemezése</span><span class="sxs-lookup"><span data-stu-id="5a1f0-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="5a1f0-129">A műveleti ablaktáblán válassza ki az **Ütemezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="5a1f0-130">Válassza ki a **Feladatok ütemezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="5a1f0-131">Az **Ütemezés iránya** mezőben válassza ki a **Szállítási dátumtól előre** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="5a1f0-132">Adjon meg egy dátumot az **Ütemezési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="5a1f0-133">Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="5a1f0-134">Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="5a1f0-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-135">Select **OK**.</span></span>
6. <span data-ttu-id="5a1f0-136">A műveleti ablaktáblán válassza ki a **Termelési rendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="5a1f0-137">Válassza ki a **Minden feladat** elemet.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-137">Select **All jobs**.</span></span> <span data-ttu-id="5a1f0-138">Vegye figyelembe, hogy az aktív útvonal alapján a feladatütemezéssel 5 feladat jött létre.</span><span class="sxs-lookup"><span data-stu-id="5a1f0-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

