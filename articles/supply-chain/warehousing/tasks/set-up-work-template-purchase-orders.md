---
title: Munkasablon beállítása beszerzési rendelésekhez
description: Ez a témakör a bevételezett cikkek betárolásakor alkalmazandó egyszerű munkasablon beállítását ismerteti.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe0b6f9b966a5ce31af9da74a2038877debd2e7c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215745"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="5abf5-103">Munkasablon beállítása beszerzési rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="5abf5-103">Set up a work template for purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5abf5-104">Ez a témakör a bevételezett cikkek betárolásakor alkalmazandó egyszerű munkasablon beállítását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="5abf5-104">This topic describes how to set up a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="5abf5-105">A munkasablonok határozzák meg a raktári dolgozó számára mobilkészüléken biztosított utasításkészletet, amikor cikkeket helyez át a bevételezési területről.</span><span class="sxs-lookup"><span data-stu-id="5abf5-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="5abf5-106">Használhatja ezt az eljárást a USMF bemutatócégnél említett adatokkal.</span><span class="sxs-lookup"><span data-stu-id="5abf5-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="5abf5-107">Mielőtt belekezdene ebbe az útmutatóba, hozzon létre egy munkagyűjtő-azonosítót.</span><span class="sxs-lookup"><span data-stu-id="5abf5-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="5abf5-108">Ebben a példában egy a Bejövőben meghívott munkagyűjtő-azonosítót használunk.</span><span class="sxs-lookup"><span data-stu-id="5abf5-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="5abf5-109">Ezt az eljárást a raktári vezető használja.</span><span class="sxs-lookup"><span data-stu-id="5abf5-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="5abf5-110">A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Munka > Munkasablonok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5abf5-110">In the navigation pane, go to **Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="5abf5-111">A **Munka rendeléstípusa** mezőben válassza ki a **Beszerzési rendelések** elemet.</span><span class="sxs-lookup"><span data-stu-id="5abf5-111">In the **Work order type** field, select **Purchase orders**.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="5abf5-112">Munkasablonfejléc létrehozása</span><span class="sxs-lookup"><span data-stu-id="5abf5-112">Create a work template header</span></span>
1. <span data-ttu-id="5abf5-113">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-113">Select **New**.</span></span>
2. <span data-ttu-id="5abf5-114">Adjon meg egy számot a **Sorozatszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5abf5-114">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="5abf5-115">A munkasablonok kiértékelése ebben a sorrendben történik.</span><span class="sxs-lookup"><span data-stu-id="5abf5-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="5abf5-116">A sorrendet módosíthatja ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="5abf5-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="5abf5-117">Írjon be egy értéket a **Munkasablon** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-117">In the **Work template** field, type a value.</span></span> <span data-ttu-id="5abf5-118">Ez ennek a sablonnak az egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5abf5-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="5abf5-119">Írjon be egy értéket a **Munkasablon leírása** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-119">In the **Work template description** field, type a value.</span></span>
    - <span data-ttu-id="5abf5-120">Amíg nem töltött ki a sablonhoz szükséges minden információt, és nem kattintott a **Mentés** gombra, az **Érvényes** lehetőség nem lesz bejelölve.</span><span class="sxs-lookup"><span data-stu-id="5abf5-120">The **Valid** option will not be checked until you've completed all the information that's needed by the template and have then selected **Save**.</span></span>  
    - <span data-ttu-id="5abf5-121">Egy **Beszerzési rendelés** típusú munkarendelést nem lehet automatikusan feldolgozni, ezért az **Automatikus feldolgozás** lehetőségnél meg kell tartani a **Nem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="5abf5-121">A work order of type **Purchase order** cannot be automatically processed, so leave the **Automatically process** option set to **No**.</span></span>  
5. <span data-ttu-id="5abf5-122">Írjon be egy értéket a **Munkagyűjtő azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-122">In the **Work pool ID** field, type a value.</span></span> <span data-ttu-id="5abf5-123">A munkagyűjtők azonosítói segítségével a munkát csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="5abf5-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="5abf5-124">Az itt beállított érték lesz az alapértelmezett érték minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="5abf5-124">The value that you set here will be the default value for any work that's created using this template.</span></span>  
6. <span data-ttu-id="5abf5-125">Írja be az `1` értéket a **Munkaprioritás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-125">In the **Work priority** field, enter `1`.</span></span> <span data-ttu-id="5abf5-126">Ez a munka fontosságát jelzi, és az itt beállított érték lesz az alapértelmezett minden ezzel a sablonnal létrehozott munka esetében.</span><span class="sxs-lookup"><span data-stu-id="5abf5-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="5abf5-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-127">Select **Save**.</span></span> <span data-ttu-id="5abf5-128">El kell menteni a munkasablon fejlécét, mielőtt a **Lekérdezés szerkesztése** gomb elérhetővé válna.</span><span class="sxs-lookup"><span data-stu-id="5abf5-128">You must save the work template header before the **Edit Query** button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="5abf5-129">A munkasablonhoz használt lekérdezés beállítása</span><span class="sxs-lookup"><span data-stu-id="5abf5-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="5abf5-130">Válassza ki a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-130">Select **Edit query**.</span></span> <span data-ttu-id="5abf5-131">Be fogunk állítani egy korlátozást, amely következtében a sablon csak egy konkrét raktárban lesz használható.</span><span class="sxs-lookup"><span data-stu-id="5abf5-131">We'll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="5abf5-132">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-132">Select **Add**.</span></span>
3. <span data-ttu-id="5abf5-133">Az új sor **Mező** mezőjében adja meg a `warehouse` értéket.</span><span class="sxs-lookup"><span data-stu-id="5abf5-133">In the **Field** field of the new row, type `warehouse`.</span></span>
4. <span data-ttu-id="5abf5-134">Adjon meg egy értéket a **Feltétel** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5abf5-134">In the **Criteria** field, type a value.</span></span>
5. <span data-ttu-id="5abf5-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-135">Select **OK**.</span></span>
6. <span data-ttu-id="5abf5-136">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-136">Select **Yes**.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="5abf5-137">Munkasablonrészletek beállítása</span><span class="sxs-lookup"><span data-stu-id="5abf5-137">Set work template details</span></span>
1. <span data-ttu-id="5abf5-138">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-138">Select **New**.</span></span>
2. <span data-ttu-id="5abf5-139">A **Munkatípus** mezőben válassza a **Kitárolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-139">In the **Work type** field, select **Pick**.</span></span>
3. <span data-ttu-id="5abf5-140">Írja be, hogy `purchase` a **Munkagyűjtő-azonosító** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-140">In the **Work class ID** field, type `purchase`.</span></span> <span data-ttu-id="5abf5-141">Az itt beállított munkaosztály lesz az alapértelmezett minden olyan Kitárolás típusú munkasor esetében, amelyet ezzel a sablonnal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="5abf5-141">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="5abf5-142">A munkaosztályt nem lehet felülbírálni a munka rendeléssorokból.</span><span class="sxs-lookup"><span data-stu-id="5abf5-142">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="5abf5-143">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="5abf5-143">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="5abf5-144">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-144">Select **New**.</span></span>
5. <span data-ttu-id="5abf5-145">A **Munkatípus** mezőben válassza a **Betárolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-145">In the **Work type** field, select **Put**.</span></span>
6. <span data-ttu-id="5abf5-146">Írjon be egy értéket a **Munkaosztály** azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5abf5-146">In the **Work class ID** field, type a value.</span></span> <span data-ttu-id="5abf5-147">A kitárolási és a betárolási utasítások egy készletet alkotnak.</span><span class="sxs-lookup"><span data-stu-id="5abf5-147">The pick and put instructions are a set.</span></span> <span data-ttu-id="5abf5-148">Minden kitárolás/betárolás-készletnek ugyanabba a munkaosztályba kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="5abf5-148">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="5abf5-149">Ugyanazt a munkaosztályt használja, amelyet megadott a kitárolási utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="5abf5-149">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="5abf5-150">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5abf5-150">Select **Save**.</span></span> <span data-ttu-id="5abf5-151">Az **Érvényes** jelölőnégyzet most már be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="5abf5-151">Note that the **Valid** checkbox is now checked.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]