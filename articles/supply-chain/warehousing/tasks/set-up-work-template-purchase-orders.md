--- 
title: "A beszerzési rendelések munkasablonjának beállítása"
description: "Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fbbe019bdca2d5182466a20370418a14032fe63d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="bc7d7-103">A beszerzési rendelések munkasablonjának beállítása</span><span class="sxs-lookup"><span data-stu-id="bc7d7-103">Set up a work template for purchase orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc7d7-104">Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="bc7d7-105">A munkasablonok határozzák meg a raktári dolgozó számára mobilkészüléken biztosított utasításkészletet, amikor cikkeket helyez át a bevételezési területről.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="bc7d7-106">Használhatja ezt az eljárást a USMF bemutatócégnél említett adatokkal.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="bc7d7-107">Mielőtt belekezdene ebbe az útmutatóba, hozzon létre egy munkagyűjtő-azonosítót.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="bc7d7-108">Ebben a példában egy a Bejövőben meghívott munkagyűjtő-azonosítót használunk.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="bc7d7-109">Ezt az eljárást a raktári vezető használja.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="bc7d7-110">Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="bc7d7-111">A Munka rendeléstípus mezőben válassza ki a „Beszerzési rendelések” elemet.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="bc7d7-112">Munkasablonfejléc létrehozása</span><span class="sxs-lookup"><span data-stu-id="bc7d7-112">Create a work template header</span></span>
1. <span data-ttu-id="bc7d7-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-113">Click New.</span></span>
2. <span data-ttu-id="bc7d7-114">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="bc7d7-115">A munkasablonok kiértékelése ebben a sorrendben történik.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="bc7d7-116">A sorrendet módosíthatja ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="bc7d7-117">Írjon be egy értéket a Munkasablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="bc7d7-118">Ez ennek a sablonnak az egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="bc7d7-119">Írjon be egy értéket a Munkasablon leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="bc7d7-120">Amíg nem töltött ki a sablonhoz szüksége minden információt, és kattintott ezután a Mentés gombra, az Érvényes lehetőség nem lesz bejelölve.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="bc7d7-121">Egy Beszerzési rendelés típusú munkarendelést nem lehet automatikusan feldolgozni, ezért az Automatikus feldolgozás lehetőségnél meg kell tartani a Nem beállítást.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="bc7d7-122">Írjon be egy értéket a Munkagyűjtő-azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="bc7d7-123">A munkagyűjtők azonosítói segítségével a munkát csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="bc7d7-124">Az itt beállított érték lesz az alapértelmezett érték minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="bc7d7-125">Írja be az „1” értéket a Munkaprioritás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="bc7d7-126">Ez a munka fontosságát jelzi, és az itt beállított érték lesz az alapértelmezett minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="bc7d7-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-127">Click Save.</span></span>
    * <span data-ttu-id="bc7d7-128">El kell menteni a munkasablon fejlécét, mielőtt a Lekérdezés szerkesztése gomb elérhetővé válna.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="bc7d7-129">A munkasablonhoz használt lekérdezés beállítása</span><span class="sxs-lookup"><span data-stu-id="bc7d7-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="bc7d7-130">Kattintson A lekérdezés szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-130">Click Edit query.</span></span>
    * <span data-ttu-id="bc7d7-131">Be fogunk állítani egy korlátozást, amely következtében a sablon csak egy konkrét raktárban lesz használható.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="bc7d7-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-132">Click Add.</span></span>
3. <span data-ttu-id="bc7d7-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="bc7d7-134">A Mező mezőbe írja be, hogy „raktár”.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="bc7d7-135">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="bc7d7-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-136">Click OK.</span></span>
7. <span data-ttu-id="bc7d7-137">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="bc7d7-138">Munkasablonrészletek beállítása</span><span class="sxs-lookup"><span data-stu-id="bc7d7-138">Set work template details</span></span>
1. <span data-ttu-id="bc7d7-139">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-139">Click New.</span></span>
2. <span data-ttu-id="bc7d7-140">A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="bc7d7-141">Írja be, hogy „beszerzés” a Munkagyűjtő-azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="bc7d7-142">Az itt beállított munkaosztály lesz az alapértelmezett minden olyan Kitárolás típusú munkasor esetében, amelyet ezzel a sablonnal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="bc7d7-143">A munkaosztályt nem lehet felülbírálni a munka rendeléssorokból.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="bc7d7-144">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="bc7d7-145">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-145">Click New.</span></span>
5. <span data-ttu-id="bc7d7-146">A Munkatípus mezőben válassza a „Betárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="bc7d7-147">Írjon be egy értéket a Munkaosztály azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="bc7d7-148">A kitárolási és a betárolási utasítások egy készletet alkotnak.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="bc7d7-149">Minden kitárolás/betárolás-készletnek ugyanabba a munkaosztályba kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="bc7d7-150">Ugyanazt a munkaosztályt használja, amelyet megadott a kitárolási utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="bc7d7-151">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-151">Click Save.</span></span>
    * <span data-ttu-id="bc7d7-152">Az érvényes jelölőnégyzet most már be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-152">Note that the Valid checkbox is now checked.</span></span>  

