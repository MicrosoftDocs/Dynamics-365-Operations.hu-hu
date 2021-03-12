---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 006310d07dfa5b75941ca248736800bbb9e8e7b7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969328"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="5205f-103">Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="5205f-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5205f-104">Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.</span><span class="sxs-lookup"><span data-stu-id="5205f-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="5205f-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="5205f-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="5205f-106">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="5205f-106">Create a policy</span></span>
1. <span data-ttu-id="5205f-107">Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="5205f-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-108">Click New.</span></span>
3. <span data-ttu-id="5205f-109">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5205f-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="5205f-110">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5205f-111">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="5205f-111">Select Organization.</span></span>  
5. <span data-ttu-id="5205f-112">A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="5205f-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5205f-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="5205f-114">Felosztási szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="5205f-114">Create allocation rules</span></span>
1. <span data-ttu-id="5205f-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-115">Click New.</span></span>
2. <span data-ttu-id="5205f-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5205f-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="5205f-117">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="5205f-118">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="5205f-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="5205f-119">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="5205f-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-120">Click New.</span></span>
7. <span data-ttu-id="5205f-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5205f-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="5205f-122">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="5205f-123">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="5205f-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="5205f-124">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="5205f-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-125">Click New.</span></span>
12. <span data-ttu-id="5205f-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5205f-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="5205f-127">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="5205f-128">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="5205f-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="5205f-129">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="5205f-130">Folytassa, amíg létrehozza az összes szabályt.</span><span class="sxs-lookup"><span data-stu-id="5205f-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="5205f-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5205f-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="5205f-132">Irányelv hozzárendelése egy költség-ellenőrzőegységhez</span><span class="sxs-lookup"><span data-stu-id="5205f-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="5205f-133">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="5205f-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5205f-134">Click New.</span></span>
3. <span data-ttu-id="5205f-135">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5205f-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5205f-136">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="5205f-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="5205f-137">A szabályok naprakészek.</span><span class="sxs-lookup"><span data-stu-id="5205f-137">The rules are date-effective.</span></span> <span data-ttu-id="5205f-138">Egy felhasználó vagy a rendszer lejártnak minősítheti szabályokat, ha újabb verziót hoz létre.</span><span class="sxs-lookup"><span data-stu-id="5205f-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="5205f-139">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5205f-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="5205f-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5205f-140">Click Save.</span></span>

