---
title: Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez
description: A költségműködés a költségek fix vagy változó osztályozása.
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
ms.openlocfilehash: 16d9dceb4c2a22eab9a5ecb8501393444f20498b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841369"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="bc5a3-103">Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="bc5a3-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc5a3-104">A költségműködés a költségek fix vagy változó osztályozása.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="bc5a3-105">Az irányelvet és a megfelelő szabályokat hozzá kell rendelni egy költségellenőrző egységhez az irányelv hatályba lépése érdekében.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="bc5a3-106">Ezzel az eljárással létrehozhat egy irányelvet, majd hozzárendelheti az irányelvet egy költségellenőrző egységhez.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="bc5a3-107">Költségműködési hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="bc5a3-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="bc5a3-108">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="bc5a3-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-109">Click New.</span></span>
3. <span data-ttu-id="bc5a3-110">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-110">Click Create.</span></span>
4. <span data-ttu-id="bc5a3-111">A Dimenzióhierarchia neve mezőbe írja be a következőt: „Költségműködés hierarchiája”.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="bc5a3-112">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-113">Válassza ki a Költségösszetevőket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="bc5a3-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-114">Click Save.</span></span>
7. <span data-ttu-id="bc5a3-115">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="bc5a3-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-116">Click New.</span></span>
9. <span data-ttu-id="bc5a3-117">Írjon be egy értéket a Csomópont mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="bc5a3-118">Adja meg a Rögzített költséget.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="bc5a3-119">A fán jelölje be a „Költségműködés hierarchiája” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="bc5a3-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-120">Click New.</span></span>
12. <span data-ttu-id="bc5a3-121">Írjon be egy értéket a Csomópont mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="bc5a3-122">Adja meg a Változó költséget.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="bc5a3-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-123">Click Save.</span></span>
14. <span data-ttu-id="bc5a3-124">A fán jelölje be a „Költségműködés hierarchiája\Rögzített költség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="bc5a3-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-125">Click New.</span></span>
16. <span data-ttu-id="bc5a3-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="bc5a3-127">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-128">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="bc5a3-129">A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-130">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="bc5a3-131">A fán jelölje be a „Költségműködés hierarchiája\Változó költség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="bc5a3-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-132">Click New.</span></span>
21. <span data-ttu-id="bc5a3-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="bc5a3-134">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-135">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="bc5a3-136">A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-137">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="bc5a3-138">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="bc5a3-139">Az irányelv és a szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="bc5a3-139">Create the policy and rules</span></span>
1. <span data-ttu-id="bc5a3-140">Ugorjon a Költségkönyvelés > Irányelvek > Költségműködési irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="bc5a3-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-141">Click New.</span></span>
3. <span data-ttu-id="bc5a3-142">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="bc5a3-143">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-144">Válassza ki a most létrehozott irányelvhierarchiát.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="bc5a3-145">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-146">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-146">Select Organization.</span></span>  
6. <span data-ttu-id="bc5a3-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-147">Click Save.</span></span>
7. <span data-ttu-id="bc5a3-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-148">Click New.</span></span>
8. <span data-ttu-id="bc5a3-149">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="bc5a3-150">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-151">Bontsa ki a hierarchiát a Változó költség kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="bc5a3-152">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="bc5a3-153">Alapértelmezés szerint a változó százalékos értéke 100 százalék.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="bc5a3-154">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="bc5a3-155">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-155">Click New.</span></span>
13. <span data-ttu-id="bc5a3-156">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="bc5a3-157">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="bc5a3-158">A szabályok naprakészek, és egy felhasználó vagy a rendszer is lejárthat minősíthet egy szabályt, ha annak újabb verziója jön létre.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="bc5a3-159">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="bc5a3-160">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-160">Click Save.</span></span>

