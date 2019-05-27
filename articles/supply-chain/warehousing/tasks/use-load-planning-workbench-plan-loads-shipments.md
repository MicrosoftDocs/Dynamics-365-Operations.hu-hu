---
title: Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel
description: Ez az eljárás bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564796"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="da39a-103">Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel</span><span class="sxs-lookup"><span data-stu-id="da39a-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da39a-104">Ez az eljárás bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="da39a-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="da39a-105">Előfeltételként létrehozzuk az értékesítési rendelést először.</span><span class="sxs-lookup"><span data-stu-id="da39a-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="da39a-106">Ez az eljárás a szállítási koordinátor napi munkájának része.</span><span class="sxs-lookup"><span data-stu-id="da39a-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="da39a-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="da39a-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="da39a-108">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="da39a-108">Create a sales order</span></span>
1. <span data-ttu-id="da39a-109">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="da39a-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="da39a-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="da39a-110">Click New.</span></span>
3. <span data-ttu-id="da39a-111">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="da39a-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="da39a-112">Válassza a US-004 fiókot.</span><span class="sxs-lookup"><span data-stu-id="da39a-112">Select account US-004.</span></span>
5. <span data-ttu-id="da39a-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="da39a-113">Click OK.</span></span>
6. <span data-ttu-id="da39a-114">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="da39a-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="da39a-115">Válassza az A0001 elemet.</span><span class="sxs-lookup"><span data-stu-id="da39a-115">Select item A0001.</span></span>
    * <span data-ttu-id="da39a-116">Az A0001 engedélyezve a szállításkezelési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="da39a-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="da39a-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="da39a-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="da39a-118">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="da39a-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="da39a-119">A Raktár mezőbe írja be a 24 értéket.</span><span class="sxs-lookup"><span data-stu-id="da39a-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="da39a-120">Ebben a példában válassza ki a 24. raktárat.</span><span class="sxs-lookup"><span data-stu-id="da39a-120">In this example select warehouse 24.</span></span> <span data-ttu-id="da39a-121">A szállításkezelés és speciális raktárkezelés engedélyezve van ehhez a raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="da39a-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="da39a-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="da39a-122">Click Save.</span></span>
12. <span data-ttu-id="da39a-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="da39a-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="da39a-124">Hozzon létre egy új rakományt</span><span class="sxs-lookup"><span data-stu-id="da39a-124">Create a new load</span></span>
1. <span data-ttu-id="da39a-125">Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.</span><span class="sxs-lookup"><span data-stu-id="da39a-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="da39a-126">Kattintson az Értékesítési sorok fülre.</span><span class="sxs-lookup"><span data-stu-id="da39a-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="da39a-127">Most létrehozza a terhelést az újonnan létrehozott értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="da39a-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="da39a-128">Rakományok építhetők kínálat és kereslet alapján beszerzési rendelésekből, átmozgatási rendelésekből és értékesítési rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="da39a-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="da39a-129">A műveleti ablaktáblán kattintson a Kínálat és kereslet elemre.</span><span class="sxs-lookup"><span data-stu-id="da39a-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="da39a-130">Kattintson az Áthelyezés új rakományba gombra.</span><span class="sxs-lookup"><span data-stu-id="da39a-130">Click To new load.</span></span>
5. <span data-ttu-id="da39a-131">A Sablonazonosító betöltése mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="da39a-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="da39a-132">A Rakomány sablon meghatározza a teljes rakomány súlyának és térfogatának maximális mértékét.</span><span class="sxs-lookup"><span data-stu-id="da39a-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="da39a-133">Például a rakomány sablon jelentheti a konténer vagy teherautó méretét.</span><span class="sxs-lookup"><span data-stu-id="da39a-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="da39a-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="da39a-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="da39a-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="da39a-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="da39a-136">A rakomány díjazása és útvonaltervezése</span><span class="sxs-lookup"><span data-stu-id="da39a-136">Rate and route the load</span></span>
1. <span data-ttu-id="da39a-137">Kattintson a Minősítés és útvonaltervezés pontra.</span><span class="sxs-lookup"><span data-stu-id="da39a-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="da39a-138">Kattintson az Útvonaldíj munkaterület pontra.</span><span class="sxs-lookup"><span data-stu-id="da39a-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="da39a-139">Kattintson a Díjközpont pontra.</span><span class="sxs-lookup"><span data-stu-id="da39a-139">Click Rate shop.</span></span>
4. <span data-ttu-id="da39a-140">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="da39a-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="da39a-141">Kattintson a Hozzárendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="da39a-141">Click Assign.</span></span>
6. <span data-ttu-id="da39a-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="da39a-142">Close the page.</span></span>
7. <span data-ttu-id="da39a-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="da39a-143">Close the page.</span></span>

