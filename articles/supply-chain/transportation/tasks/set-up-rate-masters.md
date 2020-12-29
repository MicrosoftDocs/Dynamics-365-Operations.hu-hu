---
title: Díjtörzsek beállítása
description: Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cca9fd47a5d8c81d7b8a913d0a467bc113b584
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429980"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="7e008-103">Díjtörzsek beállítása</span><span class="sxs-lookup"><span data-stu-id="7e008-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7e008-104">Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="7e008-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="7e008-105">Általában a logisztikai vezető állítja be a díjnyilvántartást, a szállítmányozókkal aláírt szerződésektől függően.</span><span class="sxs-lookup"><span data-stu-id="7e008-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="7e008-106">Ebben a példában egy légi fuvarozó számára állítunk be díjnyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="7e008-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="7e008-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7e008-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="7e008-108">Felosztástörzs beállítása</span><span class="sxs-lookup"><span data-stu-id="7e008-108">Set up break master</span></span>

1. <span data-ttu-id="7e008-109">Lépjen a **Szállításkezelés > Beállítás > Minősítés > Felosztástörzs** pontra.</span><span class="sxs-lookup"><span data-stu-id="7e008-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="7e008-110">A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják.</span><span class="sxs-lookup"><span data-stu-id="7e008-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="7e008-111">Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.</span><span class="sxs-lookup"><span data-stu-id="7e008-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="7e008-112">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-112">Select **New**.</span></span>
1. <span data-ttu-id="7e008-113">A **Felosztástörzs** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="7e008-114">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="7e008-115">Az **Adattípus** mezőben válassza ki az adattípust.</span><span class="sxs-lookup"><span data-stu-id="7e008-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="7e008-116">Az **Összehasonlítás** mezőbe írja be a kért összehasonlítási értéket (operátorok használatával).</span><span class="sxs-lookup"><span data-stu-id="7e008-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="7e008-117">Írja be a felosztási értéket az **Felosztási egység** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="7e008-118">A **Részletek** szakaszban hozzon létre annyi felosztást, amennyi az árképzési szerkezetéhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="7e008-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="7e008-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="7e008-120">Díjtörzs beállítása</span><span class="sxs-lookup"><span data-stu-id="7e008-120">Set up rate master</span></span>

1. <span data-ttu-id="7e008-121">Lépjen a **Szállításkezelés > Beállítás > Minősítés > Díjjegyzék** pontra.</span><span class="sxs-lookup"><span data-stu-id="7e008-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="7e008-122">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-122">Select **New**.</span></span>
1. <span data-ttu-id="7e008-123">Érték beírása a **Díjjegyzék** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="7e008-124">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="7e008-125">Az **Értékelés metaadatok azonosítója** mód mezőben válassza a legördítő nyílat a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7e008-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="7e008-126">A díjazási metaadatok azonosítója határozza meg a díjnyilvántartáshoz szükséges adatokat, mivel ez határozza meg a szállításkezelési motor számára szükséges metaadatokat, amely a ezt a díjnyilvántartást használja.</span><span class="sxs-lookup"><span data-stu-id="7e008-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="7e008-127">Ebben a példában kattintson a P2P opció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e008-127">For this example, select the P2P option.</span></span> <span data-ttu-id="7e008-128">Ez már definiálva van a bemutató adatokban.</span><span class="sxs-lookup"><span data-stu-id="7e008-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="7e008-129">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7e008-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="7e008-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="7e008-131">Díjalap beállítása</span><span class="sxs-lookup"><span data-stu-id="7e008-131">Set up rate base</span></span>

1. <span data-ttu-id="7e008-132">Válassza ki az **Alapdíjat**.</span><span class="sxs-lookup"><span data-stu-id="7e008-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="7e008-133">Az alapdíj határozza meg a szállítmányozó díját, és felhasználható egy tarifaszerkezet létrehozásához, mivel a felosztásban meghatározott töréspontok alapján rendszerezi a díjakat.</span><span class="sxs-lookup"><span data-stu-id="7e008-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="7e008-134">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-134">Select **New**.</span></span>
3. <span data-ttu-id="7e008-135">Érték beírása az **Alapdíj** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="7e008-136">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="7e008-137">A **Felosztás** mezőben válassza ki a legördítő nyilat a a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7e008-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7e008-138">A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják.</span><span class="sxs-lookup"><span data-stu-id="7e008-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="7e008-139">Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.</span><span class="sxs-lookup"><span data-stu-id="7e008-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="7e008-140">Ebben a példában használja a súlyt.</span><span class="sxs-lookup"><span data-stu-id="7e008-140">For this example, use weight.</span></span> <span data-ttu-id="7e008-141">Ez már definiálva van a bemutató adatokban.</span><span class="sxs-lookup"><span data-stu-id="7e008-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="7e008-142">A listában válassza ki a kiemelt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7e008-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="7e008-143">A **Részletek** szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="7e008-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="7e008-144">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-144">Select **New**.</span></span>
10. <span data-ttu-id="7e008-145">A **Lerakási hely irányítószáma – kezdő érték** mezőbe írja be a „30301” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="7e008-146">A **Lerakási hely irányítószáma – befejező érték** mezőbe írja be a „30318” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="7e008-147">A **Kiszállítási hely országa** mezőbe írja be az „USA” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="7e008-148">A **<0,45 kg** mezőbe írja be a „100” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="7e008-149">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 0,45 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="7e008-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="7e008-150">A **<2,25 kg** mezőbe írja be a „300” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="7e008-151">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 2 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="7e008-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="7e008-152">A **<9 kg** mezőbe írja be a „500” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="7e008-153">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 9 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="7e008-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="7e008-154">A **<45 kg** mezőbe írja be a „1000” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="7e008-155">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 45 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="7e008-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="7e008-156">A **<450 kg** mezőbe írja be a „3000” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="7e008-157">Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 450 kilogramm.</span><span class="sxs-lookup"><span data-stu-id="7e008-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="7e008-158">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-158">Select **Save**.</span></span>
19. <span data-ttu-id="7e008-159">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e008-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="7e008-160">Díjalap hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="7e008-160">Assign rate base</span></span>

1. <span data-ttu-id="7e008-161">**Alapdíj hozzárendelés** szakasz kibontása vagy összecsukása.</span><span class="sxs-lookup"><span data-stu-id="7e008-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="7e008-162">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-162">Select **New**.</span></span>
    * <span data-ttu-id="7e008-163">Mindegyik díjnyilvántartáshoz hozzárendelhet több díjalapot.</span><span class="sxs-lookup"><span data-stu-id="7e008-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="7e008-164">Ez lehetővé teszi a különböző árpontok létrehozását az egyes szállítmányozók számára a céltól, a szolgáltatástól vagy a különböző alapdíjaktól függően.</span><span class="sxs-lookup"><span data-stu-id="7e008-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="7e008-165">Ebben az eljárásban csak egy alapdíj-hozzárendelést hoz majd létre.</span><span class="sxs-lookup"><span data-stu-id="7e008-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="7e008-166">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7e008-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="7e008-167">Az **Alapdíj** mezőben válassza ki a legördítő nyilat a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7e008-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7e008-168">A listában válassza ki a kiemelt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7e008-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="7e008-169">A **Szolgáltatás** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7e008-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7e008-170">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7e008-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7e008-171">A listában válassza ki a kiemelt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7e008-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="7e008-172">A **Felvételi hely irányítószáma** mezőbe írja be a „98052” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="7e008-173">Válassza ki, hogy melyik irányítószámról legyen érvényes ez az alapdíj-hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="7e008-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="7e008-174">A **Felvételi hely országa** mezőbe írja be az „USA” értéket.</span><span class="sxs-lookup"><span data-stu-id="7e008-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="7e008-175">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e008-175">Select **Save**.</span></span>
