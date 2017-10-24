--- 
title: "Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez"
description: "A költségműködés a költségek fix vagy változó osztályozása."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 392cb83ceb8612a2e73cc54bb2d8d40c62a6b7b6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="d7d9a-103">Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez</span><span class="sxs-lookup"><span data-stu-id="d7d9a-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7d9a-104">A költségműködés a költségek fix vagy változó osztályozása.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="d7d9a-105">Az irányelvet és a megfelelő szabályokat hozzá kell rendelni egy költségellenőrző egységhez az irányelv hatályba lépése érdekében.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="d7d9a-106">Ezzel az eljárással létrehozhat egy irányelvet, majd hozzárendelheti az irányelvet egy költségellenőrző egységhez.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="d7d9a-107">Költségműködési hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="d7d9a-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="d7d9a-108">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="d7d9a-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-109">Click New.</span></span>
3. <span data-ttu-id="d7d9a-110">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-110">Click Create.</span></span>
4. <span data-ttu-id="d7d9a-111">A Dimenzióhierarchia neve mezőbe írja be a következőt: „Költségműködés hierarchiája”.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="d7d9a-112">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-113">Válassza ki a Költségösszetevőket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="d7d9a-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-114">Click Save.</span></span>
7. <span data-ttu-id="d7d9a-115">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="d7d9a-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-116">Click New.</span></span>
9. <span data-ttu-id="d7d9a-117">Írjon be egy értéket a Csomópont mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="d7d9a-118">Adja meg a Rögzített költséget.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="d7d9a-119">A fán jelölje be a „Költségműködés hierarchiája” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="d7d9a-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-120">Click New.</span></span>
12. <span data-ttu-id="d7d9a-121">Írjon be egy értéket a Csomópont mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="d7d9a-122">Adja meg a Változó költséget.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="d7d9a-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-123">Click Save.</span></span>
14. <span data-ttu-id="d7d9a-124">A fán jelölje be a „Költségműködés hierarchiája\Rögzített költség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="d7d9a-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-125">Click New.</span></span>
16. <span data-ttu-id="d7d9a-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="d7d9a-127">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-128">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="d7d9a-129">A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-130">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="d7d9a-131">A fán jelölje be a „Költségműködés hierarchiája\Változó költség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="d7d9a-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-132">Click New.</span></span>
21. <span data-ttu-id="d7d9a-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="d7d9a-134">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-135">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="d7d9a-136">A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-137">A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="d7d9a-138">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="d7d9a-139">Az irányelv és a szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="d7d9a-139">Create the policy and rules</span></span>
1. <span data-ttu-id="d7d9a-140">Ugorjon a Költségkönyvelés > Irányelvek > Költségműködési irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="d7d9a-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-141">Click New.</span></span>
3. <span data-ttu-id="d7d9a-142">Írjon be egy értéket az Irányelv neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="d7d9a-143">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-144">Válassza ki a most létrehozott irányelvhierarchiát.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="d7d9a-145">A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-146">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-146">Select Organization.</span></span>  
6. <span data-ttu-id="d7d9a-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-147">Click Save.</span></span>
7. <span data-ttu-id="d7d9a-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-148">Click New.</span></span>
8. <span data-ttu-id="d7d9a-149">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="d7d9a-150">A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-151">Bontsa ki a hierarchiát a Változó költség kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="d7d9a-152">A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="d7d9a-153">Alapértelmezés szerint a változó százalékos értéke 100 százalék.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="d7d9a-154">Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="d7d9a-155">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-155">Click New.</span></span>
13. <span data-ttu-id="d7d9a-156">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="d7d9a-157">Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="d7d9a-158">A szabályok naprakészek, és egy felhasználó vagy a rendszer is lejárthat minősíthet egy szabályt, ha annak újabb verziója jön létre.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="d7d9a-159">A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="d7d9a-160">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d7d9a-160">Click Save.</span></span>


