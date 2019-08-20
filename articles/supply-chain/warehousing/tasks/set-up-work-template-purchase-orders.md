---
title: A beszerzési rendelések munkasablonjának beállítása
description: Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16a8b2d80e6d5445d57c171ddb4456dd8db5ecde
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847039"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="db52e-103">A beszerzési rendelések munkasablonjának beállítása</span><span class="sxs-lookup"><span data-stu-id="db52e-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db52e-104">Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd.</span><span class="sxs-lookup"><span data-stu-id="db52e-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="db52e-105">A munkasablonok határozzák meg a raktári dolgozó számára mobilkészüléken biztosított utasításkészletet, amikor cikkeket helyez át a bevételezési területről.</span><span class="sxs-lookup"><span data-stu-id="db52e-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="db52e-106">Használhatja ezt az eljárást a USMF bemutatócégnél említett adatokkal.</span><span class="sxs-lookup"><span data-stu-id="db52e-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="db52e-107">Mielőtt belekezdene ebbe az útmutatóba, hozzon létre egy munkagyűjtő-azonosítót.</span><span class="sxs-lookup"><span data-stu-id="db52e-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="db52e-108">Ebben a példában egy a Bejövőben meghívott munkagyűjtő-azonosítót használunk.</span><span class="sxs-lookup"><span data-stu-id="db52e-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="db52e-109">Ezt az eljárást a raktári vezető használja.</span><span class="sxs-lookup"><span data-stu-id="db52e-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="db52e-110">Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.</span><span class="sxs-lookup"><span data-stu-id="db52e-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="db52e-111">A Munka rendeléstípus mezőben válassza ki a „Beszerzési rendelések” elemet.</span><span class="sxs-lookup"><span data-stu-id="db52e-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="db52e-112">Munkasablonfejléc létrehozása</span><span class="sxs-lookup"><span data-stu-id="db52e-112">Create a work template header</span></span>
1. <span data-ttu-id="db52e-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db52e-113">Click New.</span></span>
2. <span data-ttu-id="db52e-114">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="db52e-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="db52e-115">A munkasablonok kiértékelése ebben a sorrendben történik.</span><span class="sxs-lookup"><span data-stu-id="db52e-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="db52e-116">A sorrendet módosíthatja ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="db52e-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="db52e-117">Írjon be egy értéket a Munkasablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="db52e-118">Ez ennek a sablonnak az egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="db52e-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="db52e-119">Írjon be egy értéket a Munkasablon leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="db52e-120">Amíg nem töltött ki a sablonhoz szüksége minden információt, és kattintott ezután a Mentés gombra, az Érvényes lehetőség nem lesz bejelölve.</span><span class="sxs-lookup"><span data-stu-id="db52e-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="db52e-121">Egy Beszerzési rendelés típusú munkarendelést nem lehet automatikusan feldolgozni, ezért az Automatikus feldolgozás lehetőségnél meg kell tartani a Nem beállítást.</span><span class="sxs-lookup"><span data-stu-id="db52e-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="db52e-122">Írjon be egy értéket a Munkagyűjtő-azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="db52e-123">A munkagyűjtők azonosítói segítségével a munkát csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="db52e-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="db52e-124">Az itt beállított érték lesz az alapértelmezett érték minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="db52e-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="db52e-125">Írja be az „1” értéket a Munkaprioritás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="db52e-126">Ez a munka fontosságát jelzi, és az itt beállított érték lesz az alapértelmezett minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="db52e-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="db52e-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db52e-127">Click Save.</span></span>
    * <span data-ttu-id="db52e-128">El kell menteni a munkasablon fejlécét, mielőtt a Lekérdezés szerkesztése gomb elérhetővé válna.</span><span class="sxs-lookup"><span data-stu-id="db52e-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="db52e-129">A munkasablonhoz használt lekérdezés beállítása</span><span class="sxs-lookup"><span data-stu-id="db52e-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="db52e-130">Kattintson A lekérdezés szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="db52e-130">Click Edit query.</span></span>
    * <span data-ttu-id="db52e-131">Be fogunk állítani egy korlátozást, amely következtében a sablon csak egy konkrét raktárban lesz használható.</span><span class="sxs-lookup"><span data-stu-id="db52e-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="db52e-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="db52e-132">Click Add.</span></span>
3. <span data-ttu-id="db52e-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="db52e-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="db52e-134">A Mező mezőbe írja be, hogy „raktár”.</span><span class="sxs-lookup"><span data-stu-id="db52e-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="db52e-135">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="db52e-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="db52e-136">Click OK.</span></span>
7. <span data-ttu-id="db52e-137">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="db52e-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="db52e-138">Munkasablonrészletek beállítása</span><span class="sxs-lookup"><span data-stu-id="db52e-138">Set work template details</span></span>
1. <span data-ttu-id="db52e-139">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db52e-139">Click New.</span></span>
2. <span data-ttu-id="db52e-140">A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="db52e-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="db52e-141">Írja be, hogy „beszerzés” a Munkagyűjtő-azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="db52e-142">Az itt beállított munkaosztály lesz az alapértelmezett minden olyan Kitárolás típusú munkasor esetében, amelyet ezzel a sablonnal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="db52e-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="db52e-143">A munkaosztályt nem lehet felülbírálni a munka rendeléssorokból.</span><span class="sxs-lookup"><span data-stu-id="db52e-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="db52e-144">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="db52e-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="db52e-145">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db52e-145">Click New.</span></span>
5. <span data-ttu-id="db52e-146">A Munkatípus mezőben válassza a „Betárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="db52e-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="db52e-147">Írjon be egy értéket a Munkaosztály azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db52e-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="db52e-148">A kitárolási és a betárolási utasítások egy készletet alkotnak.</span><span class="sxs-lookup"><span data-stu-id="db52e-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="db52e-149">Minden kitárolás/betárolás-készletnek ugyanabba a munkaosztályba kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="db52e-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="db52e-150">Ugyanazt a munkaosztályt használja, amelyet megadott a kitárolási utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="db52e-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="db52e-151">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db52e-151">Click Save.</span></span>
    * <span data-ttu-id="db52e-152">Az érvényes jelölőnégyzet most már be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="db52e-152">Note that the Valid checkbox is now checked.</span></span>  

