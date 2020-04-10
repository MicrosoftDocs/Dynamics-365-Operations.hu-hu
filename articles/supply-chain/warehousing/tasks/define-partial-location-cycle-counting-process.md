---
title: 'Részleges ciklikus leltározásos helyfolyamat meghatározása '
description: A ciklikus leltározási tervek leltározási munka létrehozásakor történő használata esetén a tényleges leltározási műveleteket úgy irányíthatja, hogy kizárólag bizonyos termékek és termékváltozatok leltározását kéri a helyszínen lévő összes aktuális készlet helyett.
author: ShylaThompson
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67f719d5990a4331559cab34412bf82f15eca735
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148354"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="369fb-103">Részleges ciklikus leltározásos helyfolyamat meghatározása </span><span class="sxs-lookup"><span data-stu-id="369fb-103">Define partial location cycle counting process</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="369fb-104">A ciklikus leltározási tervek leltározási munka létrehozásakor történő használata esetén a tényleges leltározási műveleteket úgy irányíthatja, hogy kizárólag bizonyos termékek és termékváltozatok leltározását kéri a helyszínen lévő összes aktuális készlet helyett.</span><span class="sxs-lookup"><span data-stu-id="369fb-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="369fb-105">Adott termékekre való szűréssel a raktárvezető csökkentheti az ellenőrzéssel járó költségeket, elkerülheti a konszolidációs hibákat és időt takaríthat meg.</span><span class="sxs-lookup"><span data-stu-id="369fb-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="369fb-106">A raktár vezetője általában a beállítási feladatokat hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="369fb-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="369fb-107">Ezt a folyamatot az USMF bemutatócégen vagy saját adatain is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="369fb-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="369fb-108">Ciklikus leltározási munkasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="369fb-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="369fb-109">Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.</span><span class="sxs-lookup"><span data-stu-id="369fb-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="369fb-110">A Munkarendelés típusa mezőben válassza ki a „Ciklikus leltározás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="369fb-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="369fb-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-111">Click New.</span></span>
4. <span data-ttu-id="369fb-112">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="369fb-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="369fb-113">A rendezési sorrend a legkisebb számtól a legnagyobb számig tart.</span><span class="sxs-lookup"><span data-stu-id="369fb-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="369fb-114">Az értéknek nullánál (0) nagyobbnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="369fb-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="369fb-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="369fb-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="369fb-116">Írjon be egy értéket a Munkasablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="369fb-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="369fb-117">Írjon be egy értéket a Munkasablon leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="369fb-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="369fb-118">A Munkagyűjtő azonosítója mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="369fb-119">Adjon meg egy számot a Munka prioritása mezőben.</span><span class="sxs-lookup"><span data-stu-id="369fb-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="369fb-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="369fb-120">Click Save.</span></span>
11. <span data-ttu-id="369fb-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-121">Click New.</span></span>
12. <span data-ttu-id="369fb-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="369fb-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="369fb-123">A Munkatípus mezőben válassza a „Leltár” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="369fb-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="369fb-124">A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="369fb-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="369fb-125">Click Save.</span></span>
16. <span data-ttu-id="369fb-126">Kattintson a Munkasorszünetek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="369fb-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-127">Click New.</span></span>
18. <span data-ttu-id="369fb-128">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="369fb-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="369fb-129">A rendezési sorrend a legkisebb számtól a legnagyobb számig tart.</span><span class="sxs-lookup"><span data-stu-id="369fb-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="369fb-130">Az értéknek nullánál (0) nagyobbnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="369fb-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="369fb-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="369fb-131">Click Save.</span></span>
20. <span data-ttu-id="369fb-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="369fb-132">Close the page.</span></span>
21. <span data-ttu-id="369fb-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="369fb-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="369fb-134">Ciklikus leltározási terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="369fb-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="369fb-135">Ugorjon a Raktárkezelés > Beállítás > Ciklikus leltározás > Ciklikus leltározási tervek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="369fb-136">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-136">Click New.</span></span>
3. <span data-ttu-id="369fb-137">A Ciklikus leltározási terv azonosítója mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="369fb-138">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="369fb-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="369fb-139">A Ciklikus leltározások maximális száma mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="369fb-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="369fb-140">A Munkasablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="369fb-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-141">Click New.</span></span>
8. <span data-ttu-id="369fb-142">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="369fb-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="369fb-143">A rendezési sorrend a legkisebb számtól a legnagyobb számig tart.</span><span class="sxs-lookup"><span data-stu-id="369fb-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="369fb-144">Az értéknek nullánál (0) nagyobbnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="369fb-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="369fb-145">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="369fb-146">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="369fb-146">Click Save.</span></span>
11. <span data-ttu-id="369fb-147">Kattintson a Terméklekérdezés megadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="369fb-147">Click Define product query.</span></span>
12. <span data-ttu-id="369fb-148">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="369fb-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="369fb-149">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="369fb-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="369fb-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="369fb-150">Click OK.</span></span>
15. <span data-ttu-id="369fb-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="369fb-151">Close the page.</span></span>

