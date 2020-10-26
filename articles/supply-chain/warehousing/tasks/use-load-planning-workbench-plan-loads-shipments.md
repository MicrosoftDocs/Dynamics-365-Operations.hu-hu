---
title: Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel
description: Ez a témakör bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7966c6e445e0e44cd4ff8518926aa6b410502e13
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980435"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="49e30-103">Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel</span><span class="sxs-lookup"><span data-stu-id="49e30-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="49e30-104">Ez a témakör bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="49e30-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="49e30-105">Előfeltételként létrehozzuk az értékesítési rendelést először.</span><span class="sxs-lookup"><span data-stu-id="49e30-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="49e30-106">Ez az eljárás a szállítási koordinátor napi munkájának része.</span><span class="sxs-lookup"><span data-stu-id="49e30-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="49e30-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="49e30-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="49e30-108">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="49e30-108">Create a sales order</span></span>
1. <span data-ttu-id="49e30-109">Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="49e30-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders** .</span></span>
2. <span data-ttu-id="49e30-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-110">Select **New** .</span></span>
3. <span data-ttu-id="49e30-111">A **Vevői számla** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="49e30-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="49e30-112">Válassza ki az **US-004** fiókot.</span><span class="sxs-lookup"><span data-stu-id="49e30-112">Select account **US-004** .</span></span>
5. <span data-ttu-id="49e30-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-113">Select **OK** .</span></span>
6. <span data-ttu-id="49e30-114">A **Cikkszám** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="49e30-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="49e30-115">Válassza ki a **A0001** tételt.</span><span class="sxs-lookup"><span data-stu-id="49e30-115">Select item **A0001** .</span></span> <span data-ttu-id="49e30-116">Az **A0001** engedélyezve van a szállításkezelési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="49e30-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="49e30-117">A **Hely** mezőben kattintson a legördítő gombra a keresőlista megnyitásához, majd válasszon egy tételt.</span><span class="sxs-lookup"><span data-stu-id="49e30-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="49e30-118">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="49e30-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="49e30-119">A **Raktár** mezőben ennél a példánál adja meg a „24” értéket.</span><span class="sxs-lookup"><span data-stu-id="49e30-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="49e30-120">A szállításkezelés és speciális raktárkezelés engedélyezve van ehhez a raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="49e30-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="49e30-121">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-121">Select **Save** .</span></span>
12. <span data-ttu-id="49e30-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49e30-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="49e30-123">Hozzon létre egy új rakományt</span><span class="sxs-lookup"><span data-stu-id="49e30-123">Create a new load</span></span>
1. <span data-ttu-id="49e30-124">Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Tervezés > Rakománytervezés munkaterülete** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="49e30-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench** .</span></span>
2. <span data-ttu-id="49e30-125">Válassza ki az **Eladási sorok** fület. Ön most létrehozza a terhelést az újonnan létrehozott értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="49e30-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="49e30-126">Rakományok építhetők kínálat és kereslet alapján beszerzési rendelésekből, átmozgatási rendelésekből és értékesítési rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="49e30-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="49e30-127">A Műveleti ablaktáblán válassza ki a **Kínálat és kereslet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-127">On the Action Pane, select **Supply and demand** .</span></span>
4. <span data-ttu-id="49e30-128">Válassza ki az **Új rakományba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-128">Select **To new load** .</span></span>
5. <span data-ttu-id="49e30-129">A **Sablonazonosító betöltése** mezőben kattintson a legördítő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="49e30-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="49e30-130">A Rakomány sablon meghatározza a teljes rakomány súlyának és térfogatának maximális mértékét.</span><span class="sxs-lookup"><span data-stu-id="49e30-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="49e30-131">Például a rakomány sablon jelentheti a konténer vagy teherautó méretét.</span><span class="sxs-lookup"><span data-stu-id="49e30-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="49e30-132">Válasszon ki egy cikket.</span><span class="sxs-lookup"><span data-stu-id="49e30-132">Select an item.</span></span>
6. <span data-ttu-id="49e30-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-133">Select **OK** .</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="49e30-134">A rakomány díjazása és útvonaltervezése</span><span class="sxs-lookup"><span data-stu-id="49e30-134">Rate and route the load</span></span>
1. <span data-ttu-id="49e30-135">Válassza ki a **Minősítés és útvonaltervezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-135">Select **Rating and routing** .</span></span>
2. <span data-ttu-id="49e30-136">Válassza ki az **Útvonal-díj munkaterület** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-136">Select **Rate route workbench** .</span></span>
3. <span data-ttu-id="49e30-137">Válassza ki a **Díjközpont** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-137">Select **Rate shop** .</span></span>
4. <span data-ttu-id="49e30-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="49e30-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="49e30-139">Válassza ki a **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49e30-139">Select **Assign** .</span></span>
6. <span data-ttu-id="49e30-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="49e30-140">Close the page.</span></span>

