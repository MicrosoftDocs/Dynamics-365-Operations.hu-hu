---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822855"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="d1949-103">Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="d1949-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1949-104">Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.</span><span class="sxs-lookup"><span data-stu-id="d1949-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="d1949-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="d1949-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="d1949-106">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="d1949-106">Create a policy</span></span>
1. <span data-ttu-id="d1949-107">Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="d1949-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-108">Click New.</span></span>
3. <span data-ttu-id="d1949-109">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d1949-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="d1949-110">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="d1949-111">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="d1949-111">Select Organization.</span></span>  
5. <span data-ttu-id="d1949-112">A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="d1949-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d1949-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="d1949-114">Felosztási szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="d1949-114">Create allocation rules</span></span>
1. <span data-ttu-id="d1949-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-115">Click New.</span></span>
2. <span data-ttu-id="d1949-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d1949-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="d1949-117">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="d1949-118">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1949-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="d1949-119">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="d1949-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-120">Click New.</span></span>
7. <span data-ttu-id="d1949-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d1949-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="d1949-122">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="d1949-123">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1949-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="d1949-124">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="d1949-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-125">Click New.</span></span>
12. <span data-ttu-id="d1949-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d1949-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="d1949-127">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="d1949-128">Válassza az Összes lehetőséget a Költség működése mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1949-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="d1949-129">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="d1949-130">Folytassa, amíg létrehozza az összes szabályt.</span><span class="sxs-lookup"><span data-stu-id="d1949-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="d1949-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d1949-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="d1949-132">Irányelv hozzárendelése egy költség-ellenőrzőegységhez</span><span class="sxs-lookup"><span data-stu-id="d1949-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="d1949-133">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="d1949-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1949-134">Click New.</span></span>
3. <span data-ttu-id="d1949-135">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d1949-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d1949-136">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1949-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="d1949-137">A szabályok naprakészek.</span><span class="sxs-lookup"><span data-stu-id="d1949-137">The rules are date-effective.</span></span> <span data-ttu-id="d1949-138">Egy felhasználó vagy a rendszer lejártnak minősítheti szabályokat, ha újabb verziót hoz létre.</span><span class="sxs-lookup"><span data-stu-id="d1949-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="d1949-139">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1949-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="d1949-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d1949-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]