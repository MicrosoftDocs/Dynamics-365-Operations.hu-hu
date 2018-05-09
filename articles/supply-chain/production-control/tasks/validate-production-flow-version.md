--- 
title: "Termelési folyamat és verzió érvényesítése"
description: "Ez az eljárás bemutatja, hogyan hozhat létre új termelési folyamatot és első verziót lean manufacturing esetén."
author: ChristianRytt
manager: AnnBe
ms.date: 02/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: bc563eac09fffc191a34041da7c91e7a3ffbd2e1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="9deea-103">Termelési folyamat és verzió érvényesítése</span><span class="sxs-lookup"><span data-stu-id="9deea-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9deea-104">Ez az eljárás bemutatja, hogyan hozhat létre új termelési folyamatot és első verziót lean manufacturing esetén.</span><span class="sxs-lookup"><span data-stu-id="9deea-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="9deea-105">Előfeltételek: Ehhez az eljáráshoz meg kell adni a Lean manufacturingre vonatkozó termelési paramétereket és a mértékegységeket.</span><span class="sxs-lookup"><span data-stu-id="9deea-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="9deea-106">Meg kell adnia egy Érték-előállítási folyamatot és egy Termelési csoportot is.</span><span class="sxs-lookup"><span data-stu-id="9deea-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="9deea-107">További információt a termelési folyamatokról és a lean manufacturing tevékenységeiről a Lean manufacturing témájáról szóló tanulmányokban talál.</span><span class="sxs-lookup"><span data-stu-id="9deea-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="9deea-108">Ez az eljárás az USMF jogi személyre utal a bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="9deea-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="9deea-109">Ugyanakkor, ha az adott jogi személy lean manufacturingre van konfigurálva, akkor más jogi személy is használható.</span><span class="sxs-lookup"><span data-stu-id="9deea-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="9deea-110">Termelési folyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="9deea-110">Create a production flow</span></span>
1. <span data-ttu-id="9deea-111">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9deea-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="9deea-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9deea-112">Click New.</span></span>
3. <span data-ttu-id="9deea-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9deea-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="9deea-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9deea-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9deea-115">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9deea-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9deea-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9deea-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9deea-117">Az érték-előállítási folyamat egy olyan üzemi egység, amely az érték-előállítási folyamat minden tevékenységére és folyamatára kiterjed.</span><span class="sxs-lookup"><span data-stu-id="9deea-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="9deea-118">Ebben a szakaszban az üzemi egységeknek csak egy jogi személye lehet, és nincs további funkciójuk.</span><span class="sxs-lookup"><span data-stu-id="9deea-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="9deea-119">A Gyártási csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9deea-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9deea-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9deea-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9deea-121">A termelési csoportokkal meghatározhatja a termelési folyamat anyagát, munkáját és a befejezetlen termelés fiókjait.</span><span class="sxs-lookup"><span data-stu-id="9deea-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="9deea-122">A termelési folyamat könyvelési környezethez való társításához ki kell választani egy termelési csoportot.</span><span class="sxs-lookup"><span data-stu-id="9deea-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="9deea-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9deea-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="9deea-124">Termelési folyamat verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="9deea-124">Create a production flow version</span></span>
1. <span data-ttu-id="9deea-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9deea-125">Click Add.</span></span>
2. <span data-ttu-id="9deea-126">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="9deea-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="9deea-127">A verzió lejárati dátumát bármikor frissítheti, akár aktív verziók esetén is.</span><span class="sxs-lookup"><span data-stu-id="9deea-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="9deea-128">Egy verzió kivezetésének tervezéséhez használja a verzió lejáratát.</span><span class="sxs-lookup"><span data-stu-id="9deea-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="9deea-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9deea-129">Click OK.</span></span>
4. <span data-ttu-id="9deea-130">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9deea-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="9deea-131">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9deea-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="9deea-132">Válassza ki a taktegységet.</span><span class="sxs-lookup"><span data-stu-id="9deea-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="9deea-133">Az Átlagos taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9deea-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="9deea-134">A termelésifolyamat-verzió taktellenőrzéshez adjon meg egy célzott átlagos taktidőt.</span><span class="sxs-lookup"><span data-stu-id="9deea-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="9deea-135">A takt a mennyiség egy adott időszakra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="9deea-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="9deea-136">Ebben a példában a taktidő 0,2 óra/10 darab.</span><span class="sxs-lookup"><span data-stu-id="9deea-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="9deea-137">8 órás munkaidővel ez 400 darabos napi termelési kapacitásnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="9deea-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="9deea-138">Adjon meg egy számot a Mennyiség/ciklus mezőben.</span><span class="sxs-lookup"><span data-stu-id="9deea-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="9deea-139">Bontsa ki vagy csukja össze a Verzióadatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9deea-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="9deea-140">A Minimum taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9deea-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="9deea-141">A minimális taktidő kisebb vagy egyenlő lehet az átlagos taktidővel.</span><span class="sxs-lookup"><span data-stu-id="9deea-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="9deea-142">A Maximum taktidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9deea-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="9deea-143">A maximális taktidő nagyobb vagy egyenlő lehet az átlagos taktidővel.</span><span class="sxs-lookup"><span data-stu-id="9deea-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="9deea-144">Adja meg az Időszak a tényleges ciklusidőhöz napjainak a számát</span><span class="sxs-lookup"><span data-stu-id="9deea-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="9deea-145">A tényleges ciklusidő időszaka a feladatok által összesített napok száma a tényleges perctől visszafelé, a tényleges ciklusidő kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="9deea-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="9deea-146">Az érték bármikor módosítható, és azt csak a tényleges ciklusidők kiszámításához használjuk.</span><span class="sxs-lookup"><span data-stu-id="9deea-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="9deea-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9deea-147">Click Save.</span></span>


