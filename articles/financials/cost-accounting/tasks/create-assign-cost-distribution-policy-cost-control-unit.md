---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d040f9495c7fb36985b5f96c15ac43aa226da24
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841321"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="1f949-103">Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="1f949-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f949-104">A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket.</span><span class="sxs-lookup"><span data-stu-id="1f949-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="1f949-105">A költségkönyvelő meggyőződik arról, hogy a rendszer a költséget a kiválasztott felosztási alap szerint osztja el a költséghelyek között.</span><span class="sxs-lookup"><span data-stu-id="1f949-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="1f949-106">Az irányelv és a kapcsolódó szabályok a költség-ellenőrzőegységhez vannak rendelve.</span><span class="sxs-lookup"><span data-stu-id="1f949-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="1f949-107">Ez a feladat-útmutató egy példa segítségével mutatja be a költségfelosztási irányelv és a kapcsolódó szabályok létrehozásást.</span><span class="sxs-lookup"><span data-stu-id="1f949-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="1f949-108">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f949-108">Create a policy</span></span>
1. <span data-ttu-id="1f949-109">Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="1f949-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-110">Click New.</span></span>
3. <span data-ttu-id="1f949-111">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f949-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="1f949-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1f949-113">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-114">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="1f949-114">Select Organization.</span></span>  
6. <span data-ttu-id="1f949-115">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-116">Válassza a CDS P/L lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="1f949-117">A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-118">Válassza a Statisztikai elemek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="1f949-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f949-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="1f949-120">Az irányelv szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f949-120">Create rules for the policy</span></span>
1. <span data-ttu-id="1f949-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-121">Click New.</span></span>
2. <span data-ttu-id="1f949-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1f949-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="1f949-123">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-124">Bontsa ki a hierarchiát a 094 kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1f949-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="1f949-125">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-126">Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605110 Tisztítás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="1f949-127">A Költség működése mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="1f949-128">Válassza a Rögzített költség lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="1f949-129">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="1f949-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-130">Click New.</span></span>
8. <span data-ttu-id="1f949-131">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1f949-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="1f949-132">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-133">Bontsa ki a hierarchiát a 094 kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1f949-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="1f949-134">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="1f949-135">Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605150 Bérlet lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="1f949-136">A Költség működése mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="1f949-137">Válassza a Rögzített költség lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f949-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="1f949-138">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="1f949-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f949-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="1f949-140">Szabályok hozzárendelése egy költség-ellenőrzőegységhez</span><span class="sxs-lookup"><span data-stu-id="1f949-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="1f949-141">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="1f949-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f949-142">Click New.</span></span>
3. <span data-ttu-id="1f949-143">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1f949-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="1f949-144">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f949-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="1f949-145">Válassza ki szeptember 1-jét az érvényes pénzügyi évben.</span><span class="sxs-lookup"><span data-stu-id="1f949-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="1f949-146">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f949-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="1f949-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f949-147">Click Save.</span></span>

