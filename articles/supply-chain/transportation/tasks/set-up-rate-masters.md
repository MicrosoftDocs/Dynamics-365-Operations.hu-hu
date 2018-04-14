--- 
title: "Díjtörzsek beállítása"
description: "Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a3ba01bc05d130991e8a744d9026d53edf93ee20
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-rate-masters"></a><span data-ttu-id="ba392-103">Díjtörzsek beállítása</span><span class="sxs-lookup"><span data-stu-id="ba392-103">Set up rate masters</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ba392-104">Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="ba392-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="ba392-105">Általában a logisztikai vezető állítja be a díjnyilvántartást, a szállítmányozókkal aláírt szerződésektől függően.</span><span class="sxs-lookup"><span data-stu-id="ba392-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="ba392-106">Ebben a példában egy légi fuvarozó számára állítunk be díjnyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="ba392-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="ba392-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ba392-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="ba392-108">Díjtörzs beállítása</span><span class="sxs-lookup"><span data-stu-id="ba392-108">Set up rate master</span></span>
1. <span data-ttu-id="ba392-109">Lépjen a Szállításkezelés > Beállítás > Minősítés > Díjjegyzék pontra.</span><span class="sxs-lookup"><span data-stu-id="ba392-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="ba392-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ba392-110">Click New.</span></span>
3. <span data-ttu-id="ba392-111">Érték beírása a Díjjegyzék mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ba392-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="ba392-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ba392-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ba392-113">Az Értékelés metaadatok azonosítója mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ba392-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ba392-114">A díjazási metaadatok azonosítója határozza meg a díjnyilvántartáshoz szükséges adatokat, mivel ez határozza meg a TMS-motor számára szükséges metaadatokat, amely a ezt a díjnyilvántartást használja.</span><span class="sxs-lookup"><span data-stu-id="ba392-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="ba392-115">Ebben a példában kattintson a P2P opció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ba392-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="ba392-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ba392-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ba392-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ba392-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="ba392-118">Díjalap beállítása</span><span class="sxs-lookup"><span data-stu-id="ba392-118">Set up rate base</span></span>
1. <span data-ttu-id="ba392-119">Kattintson az Alapdíj gombra.</span><span class="sxs-lookup"><span data-stu-id="ba392-119">Click Rate base.</span></span>
    * <span data-ttu-id="ba392-120">Az alapdíj határozza meg a szállítmányozó díját, és felhasználható egy tarifaszerkezet létrehozásához, mivel a felosztásban meghatározott töréspontok alapján rendszerezi a díjakat.</span><span class="sxs-lookup"><span data-stu-id="ba392-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="ba392-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ba392-121">Click New.</span></span>
3. <span data-ttu-id="ba392-122">Érték beírása az Alapdíj mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ba392-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="ba392-123">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ba392-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ba392-124">A Felosztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ba392-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ba392-125">A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják.</span><span class="sxs-lookup"><span data-stu-id="ba392-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="ba392-126">Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.</span><span class="sxs-lookup"><span data-stu-id="ba392-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="ba392-127">Ebben a példában használja a súlyt</span><span class="sxs-lookup"><span data-stu-id="ba392-127">For this example, use weight</span></span>
7. <span data-ttu-id="ba392-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ba392-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ba392-129">Bontsa ki a Részletek részt.</span><span class="sxs-lookup"><span data-stu-id="ba392-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="ba392-130">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="ba392-130">Click New.</span></span>
10. <span data-ttu-id="ba392-131">A Lerakási hely irányítószáma – kezdő érték mezőbe írja be a 30301 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="ba392-132">A Lerakási hely irányítószáma – befejező érték mezőbe írja be a 30318 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="ba392-133">A Kiszállítási hely országa mezőbe írja be az USA értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="ba392-134">A(z) 100 Lbs mezőbe írja be a 100 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="ba392-135">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint fél kilogramm.</span><span class="sxs-lookup"><span data-stu-id="ba392-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="ba392-136">A 5.00 Lbs mezőbe írja be a 300 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="ba392-137">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint két kilogramm.</span><span class="sxs-lookup"><span data-stu-id="ba392-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="ba392-138">A 20.00 Lbs mezőbe írja be a 500 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="ba392-139">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 9 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="ba392-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="ba392-140">A 100.00 Lbs mezőbe írja be az 1000 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="ba392-141">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 45 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="ba392-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="ba392-142">A <1,000.00 Lbs mezőbe írja be a 3000 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="ba392-143">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 450 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="ba392-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="ba392-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ba392-144">Click Save.</span></span>
19. <span data-ttu-id="ba392-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ba392-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="ba392-146">Díjalap hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="ba392-146">Assign rate base</span></span>
1. <span data-ttu-id="ba392-147">Az Alapdíj hozzárendelés szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="ba392-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="ba392-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ba392-148">Click New.</span></span>
    * <span data-ttu-id="ba392-149">Mindegyik díjnyilvántartáshoz hozzárendelhet több díjalapot.</span><span class="sxs-lookup"><span data-stu-id="ba392-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="ba392-150">Ez lehetővé teszi a különböző árpontok létrehozását az egyes szállítmányozók számára a céltól, a szolgáltatástól vagy a különböző alapdíjaktól függően.</span><span class="sxs-lookup"><span data-stu-id="ba392-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="ba392-151">Ebben az eljárásban csak egy alapdíj-hozzárendelést hoz majd létre.</span><span class="sxs-lookup"><span data-stu-id="ba392-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="ba392-152">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ba392-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ba392-153">Az Alapdíj mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ba392-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ba392-154">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ba392-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ba392-155">A Szolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ba392-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ba392-156">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ba392-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ba392-157">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ba392-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ba392-158">A Felvételi hely irányítószáma mezőbe írja be a 98052 értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="ba392-159">Válassza ki, hogy melyik irányítószámról legyen érvényes ez az alapdíj-hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="ba392-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="ba392-160">A Felvételi hely országa mezőbe írja be az USA értéket.</span><span class="sxs-lookup"><span data-stu-id="ba392-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="ba392-161">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ba392-161">Click Save.</span></span>


