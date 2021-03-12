---
title: Költségösszegzési irányelv létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0a648984a8b4aaa314707e72a615f516116a193
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990742"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="0876c-103">Költségösszegzési irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="0876c-103">Create a cost rollup policy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0876c-104">Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="0876c-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="0876c-105">Az eljárás létrehozásához az USP2 bemutatóadatokat használtuk.</span><span class="sxs-lookup"><span data-stu-id="0876c-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="0876c-106">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="0876c-106">Create a policy</span></span>
1. <span data-ttu-id="0876c-107">Lépjen a Költségkönyvelés > Irányelvek > Költségösszegzési irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0876c-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="0876c-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0876c-108">Click New.</span></span>
3. <span data-ttu-id="0876c-109">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0876c-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="0876c-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0876c-111">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-112">Válassza a Költségösszesítés CC lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="0876c-113">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-114">Válassza a Költségösszesítés CC lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="0876c-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0876c-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="0876c-116">Költségösszegzési irányelv szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="0876c-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="0876c-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0876c-117">Click New.</span></span>
2. <span data-ttu-id="0876c-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0876c-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="0876c-119">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-120">Válassza a 007 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-120">Select 007.</span></span>  
4. <span data-ttu-id="0876c-121">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-122">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="0876c-123">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-124">Ebben a példában rendelje a CC-007 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="0876c-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="0876c-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0876c-125">Click New.</span></span>
7. <span data-ttu-id="0876c-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0876c-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="0876c-127">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-128">Válassza a 008 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-128">Select 008.</span></span>  
9. <span data-ttu-id="0876c-129">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-130">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="0876c-131">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-132">Ebben a példában rendelje a CC-008 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="0876c-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="0876c-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0876c-133">Click New.</span></span>
12. <span data-ttu-id="0876c-134">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0876c-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="0876c-135">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-136">Válassza a 009 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-136">Select 009.</span></span>  
14. <span data-ttu-id="0876c-137">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-138">Válassza a Költségösszesítés CE lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0876c-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="0876c-139">A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0876c-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="0876c-140">Ebben a példában rendelje a CC-009 másodlagos költségösszetevőt a költséghelyhez.</span><span class="sxs-lookup"><span data-stu-id="0876c-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="0876c-141">Folytassa, amíg minden költséghely a hozzá tartozó másodlagos költségösszetevőhöz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="0876c-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="0876c-142">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0876c-142">Click Save.</span></span>

