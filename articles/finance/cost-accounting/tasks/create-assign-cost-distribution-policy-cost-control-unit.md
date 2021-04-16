---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 736b537958f65fb54d0829cfbcc819fd315b530c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810126"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="15312-103">Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="15312-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="15312-104">A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket.</span><span class="sxs-lookup"><span data-stu-id="15312-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="15312-105">A költségkönyvelő meggyőződik arról, hogy a rendszer a költséget a kiválasztott felosztási alap szerint osztja el a költséghelyek között.</span><span class="sxs-lookup"><span data-stu-id="15312-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="15312-106">Az irányelv és a kapcsolódó szabályok a költség-ellenőrzőegységhez vannak rendelve.</span><span class="sxs-lookup"><span data-stu-id="15312-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="15312-107">Ez a feladat-útmutató egy példa segítségével mutatja be a költségfelosztási irányelv és a kapcsolódó szabályok létrehozásást.</span><span class="sxs-lookup"><span data-stu-id="15312-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="15312-108">Irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="15312-108">Create a policy</span></span>
1. <span data-ttu-id="15312-109">Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="15312-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-110">Click New.</span></span>
3. <span data-ttu-id="15312-111">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="15312-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="15312-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="15312-113">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-114">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="15312-114">Select Organization.</span></span>  
6. <span data-ttu-id="15312-115">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-116">Válassza a CDS P/L lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="15312-117">A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-118">Válassza a Statisztikai elemek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="15312-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="15312-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="15312-120">Az irányelv szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="15312-120">Create rules for the policy</span></span>
1. <span data-ttu-id="15312-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-121">Click New.</span></span>
2. <span data-ttu-id="15312-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="15312-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="15312-123">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-124">Bontsa ki a hierarchiát a 094 kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="15312-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="15312-125">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-126">Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605110 Tisztítás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="15312-127">A Költség működése mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="15312-128">Válassza a Rögzített költség lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="15312-129">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="15312-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-130">Click New.</span></span>
8. <span data-ttu-id="15312-131">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="15312-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="15312-132">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-133">Bontsa ki a hierarchiát a 094 kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="15312-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="15312-134">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="15312-135">Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605150 Bérlet lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="15312-136">A Költség működése mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="15312-137">Válassza a Rögzített költség lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15312-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="15312-138">A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="15312-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="15312-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="15312-140">Szabályok hozzárendelése egy költség-ellenőrzőegységhez</span><span class="sxs-lookup"><span data-stu-id="15312-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="15312-141">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="15312-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15312-142">Click New.</span></span>
3. <span data-ttu-id="15312-143">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="15312-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="15312-144">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="15312-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="15312-145">Válassza ki szeptember 1-jét az érvényes pénzügyi évben.</span><span class="sxs-lookup"><span data-stu-id="15312-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="15312-146">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15312-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="15312-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="15312-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]