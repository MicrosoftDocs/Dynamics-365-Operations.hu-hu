--- 
title: "Költségösszegzési irányelv létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat."
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 5f1fa434061832bd306cef13afc46c7f3adab0c0
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="7ecb8-103">Költségösszegzési irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ecb8-103">Create a cost rollup policy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ecb8-104">Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="7ecb8-105">Az eljárás létrehozásához az USP2 bemutatóadatokat használtuk.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="7ecb8-106">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ecb8-106">Create a policy</span></span>
1. <span data-ttu-id="7ecb8-107">Lépjen a Költségkönyvelés > Irányelvek > Költségösszegzési irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="7ecb8-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-108">Click New.</span></span>
3. <span data-ttu-id="7ecb8-109">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="7ecb8-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7ecb8-111">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-112">Válassza a Költségösszesítés CC lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="7ecb8-113">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-114">Válassza a Költségösszesítés CC lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="7ecb8-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="7ecb8-116">Költségösszegzési irányelv szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ecb8-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="7ecb8-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-117">Click New.</span></span>
2. <span data-ttu-id="7ecb8-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="7ecb8-119">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-120">Válassza a 007 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-120">Select 007.</span></span>  
4. <span data-ttu-id="7ecb8-121">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-122">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="7ecb8-123">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-124">Ebben a példában rendelje a CC-007 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="7ecb8-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-125">Click New.</span></span>
7. <span data-ttu-id="7ecb8-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="7ecb8-127">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-128">Válassza a 008 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-128">Select 008.</span></span>  
9. <span data-ttu-id="7ecb8-129">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-130">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="7ecb8-131">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-132">Ebben a példában rendelje a CC-008 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="7ecb8-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-133">Click New.</span></span>
12. <span data-ttu-id="7ecb8-134">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="7ecb8-135">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-136">Válassza a 009 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-136">Select 009.</span></span>  
14. <span data-ttu-id="7ecb8-137">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-138">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="7ecb8-139">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7ecb8-140">Ebben a példában rendelje a CC-009 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="7ecb8-141">Folytassa, amíg minden költséghely a hozzá tartozó másodlagos költségösszetevőhöz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="7ecb8-142">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7ecb8-142">Click Save.</span></span>


