--- 
title: "Termelési folyamat verziójának létrehozása"
description: "Ez az eljárás a termelési folyamat új verziójának létrehozását foglalja össze."
author: cvocph
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 58b3c9cd265b97a814541315e4ba8378010eb2b2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="10887-103">Termelési folyamat verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="10887-103">Create a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10887-104">Ez az eljárás a termelési folyamat új verziójának létrehozását foglalja össze.</span><span class="sxs-lookup"><span data-stu-id="10887-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="10887-105">Ehhez az eljáráshoz meg kell adni a lean manufacturingre vonatkozó termelési paramétereket és a mértékegységeket.</span><span class="sxs-lookup"><span data-stu-id="10887-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="10887-106">Meg kell adnia egy érték-előállítási folyamatot és egy termelési csoportot is.</span><span class="sxs-lookup"><span data-stu-id="10887-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="10887-107">További információt a termelési folyamatokról és a lean manufacturing tevékenységeiről a Lean manufacturing a Microsoft Dynamics AX szolgáltatáshoz c. tanulmányokban talál.</span><span class="sxs-lookup"><span data-stu-id="10887-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="10887-108">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="10887-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="10887-109">Termelési folyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="10887-109">Create a production flow</span></span>
1. <span data-ttu-id="10887-110">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10887-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="10887-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10887-111">Click New.</span></span>
3. <span data-ttu-id="10887-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="10887-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="10887-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="10887-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="10887-114">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10887-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="10887-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="10887-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10887-116">Válasszon ki egy érték-előállítási folyamat típusú üzemi egységet.</span><span class="sxs-lookup"><span data-stu-id="10887-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="10887-117">Az érték-előállítási folyamat egy olyan üzemi egység, amely az érték-előállítási folyamat minden tevékenységére és folyamatára kiterjed.</span><span class="sxs-lookup"><span data-stu-id="10887-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="10887-118">Ebben a szakaszban az üzemi egységeknek csak egy jogi személye lehet, és nincs további funkciójuk.</span><span class="sxs-lookup"><span data-stu-id="10887-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="10887-119">A Gyártási csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10887-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="10887-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="10887-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10887-121">Válassza ki a termelési folyamat termelési csoportját.</span><span class="sxs-lookup"><span data-stu-id="10887-121">Select a production group for the production flow.</span></span> <span data-ttu-id="10887-122">A termelési csoportokkal meghatározhatja a termelési folyamat anyagát, munkáját és a befejezetlen termelés fiókjait.</span><span class="sxs-lookup"><span data-stu-id="10887-122">Production groups allow the definition of material, labour, and WIP accounts for a production process.</span></span> <span data-ttu-id="10887-123">A termelési folyamat könyvelési környezethez való társításához ki kell választani egy termelési csoportot.</span><span class="sxs-lookup"><span data-stu-id="10887-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="10887-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10887-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="10887-125">Termelési folyamat verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="10887-125">Create a production flow version</span></span>
1. <span data-ttu-id="10887-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="10887-126">Click Add.</span></span>
2. <span data-ttu-id="10887-127">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="10887-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="10887-128">Szükség esetén adja meg a verzió Lejárati dátumát.</span><span class="sxs-lookup"><span data-stu-id="10887-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="10887-129">Ezt bármikor, akár az aktív verzióknál is frissítheti.</span><span class="sxs-lookup"><span data-stu-id="10887-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="10887-130">Ezzel megtervezheti egy verzió kivezetését is.</span><span class="sxs-lookup"><span data-stu-id="10887-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="10887-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10887-131">Click OK.</span></span>
4. <span data-ttu-id="10887-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="10887-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="10887-133">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="10887-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="10887-134">ResolveChanges a Takt egység.</span><span class="sxs-lookup"><span data-stu-id="10887-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="10887-135">Az Átlagos taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="10887-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="10887-136">Adja meg a verzió Átlagos taktidejét.</span><span class="sxs-lookup"><span data-stu-id="10887-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="10887-137">A termelésifolyamat-verzió taktellenőrzéshez adjon meg egy célzott átlagos taktidőt.</span><span class="sxs-lookup"><span data-stu-id="10887-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="10887-138">A takt a mennyiség egy adott időszakra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="10887-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="10887-139">Ebben a példában a taktidő 0,2 óra/10 darab.</span><span class="sxs-lookup"><span data-stu-id="10887-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="10887-140">8 órás munkaidővel ez 400 darabos napi termelési kapacitásnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="10887-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="10887-141">Adjon meg egy számot a Mennyiség/ciklus mezőben.</span><span class="sxs-lookup"><span data-stu-id="10887-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="10887-142">Adja meg az átlagos taktidőhöz kapcsolódó ciklusonkénti mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="10887-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="10887-143">Bontsa ki a Verzió részletei c. részt.</span><span class="sxs-lookup"><span data-stu-id="10887-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="10887-144">A Minimum taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="10887-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="10887-145">Adja meg a minimális taktidőt.</span><span class="sxs-lookup"><span data-stu-id="10887-145">Define the minimum takt time.</span></span> <span data-ttu-id="10887-146">A minimális taktidő kisebb vagy egyenlő lehet az átlagos taktidővel.</span><span class="sxs-lookup"><span data-stu-id="10887-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="10887-147">A Maximum taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="10887-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="10887-148">A maximális taktidő nagyobb vagy egyenlő lehet az átlagos taktidővel.</span><span class="sxs-lookup"><span data-stu-id="10887-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="10887-149">Adja meg az Időszak a tényleges ciklusidőhöz (napok) mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="10887-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="10887-150">Adja meg az Időszak a tényleges ciklusidőhöz napjainak a számát.</span><span class="sxs-lookup"><span data-stu-id="10887-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="10887-151">A tényleges ciklusidő időszaka a feladatok által összesített napok száma a tényleges perctől visszafelé, a tényleges ciklusidő kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="10887-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="10887-152">Az érték bármikor módosítható, és azt csak a tényleges ciklusidők kiszámításához használjuk.</span><span class="sxs-lookup"><span data-stu-id="10887-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="10887-153">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10887-153">Click Save.</span></span>


