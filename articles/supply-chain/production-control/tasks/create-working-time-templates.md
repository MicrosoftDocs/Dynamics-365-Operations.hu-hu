--- 
title: "Munkaidősablonok készítése"
description: "A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2df37747601618fc3d45734152a05aedd39500a6
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-working-time-templates"></a><span data-ttu-id="74220-103">Munkaidősablonok készítése</span><span class="sxs-lookup"><span data-stu-id="74220-103">Create working time templates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="74220-104">A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="74220-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="74220-105">Ez az eljárás bemutatja, hogyan definiálhat munkaidősablonokat a munkaidő-ütemezési tulajdonságok segítségével a munkaidő-intervallumok kategorizálásához.</span><span class="sxs-lookup"><span data-stu-id="74220-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="74220-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="74220-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="74220-107">Ugrás az összes munkaterületek > Erőforrás életciklusa kezelése elemre.</span><span class="sxs-lookup"><span data-stu-id="74220-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="74220-108">Kattintson a Munkaidősablonok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74220-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="74220-109">Munkaidősablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="74220-109">Create working time template</span></span>
1. <span data-ttu-id="74220-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74220-110">Click New.</span></span>
2. <span data-ttu-id="74220-111">Írjon be egy értéket a Munkidősablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="74220-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="74220-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="74220-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="74220-113">Bontsa ki a Hétfő szakaszt.</span><span class="sxs-lookup"><span data-stu-id="74220-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="74220-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-114">Click Add.</span></span>
6. <span data-ttu-id="74220-115">Az Kezdés mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="74220-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="74220-116">Adja meg az időt, amikor a munka reggel elkezdődik.</span><span class="sxs-lookup"><span data-stu-id="74220-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="74220-117">A Befejezés mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="74220-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="74220-118">Adja meg a dolgozók ebédszünetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="74220-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="74220-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-119">Click Add.</span></span>
9. <span data-ttu-id="74220-120">Az Kezdés mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="74220-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="74220-121">Adja meg, hogy mikor folytatódik a munka ebéd után.</span><span class="sxs-lookup"><span data-stu-id="74220-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="74220-122">A Befejezés mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="74220-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="74220-123">A munkanap végének meghatározása.</span><span class="sxs-lookup"><span data-stu-id="74220-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="74220-124">Munkaidők átmásolása minden hétköznapra</span><span class="sxs-lookup"><span data-stu-id="74220-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="74220-125">Kattintson a Nap másolása elemre.</span><span class="sxs-lookup"><span data-stu-id="74220-125">Click Copy day.</span></span>
    * <span data-ttu-id="74220-126">Másolja át a munkaidők definícióit hétfőről keddre.</span><span class="sxs-lookup"><span data-stu-id="74220-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="74220-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-127">Click OK.</span></span>
3. <span data-ttu-id="74220-128">Kattintson a Nap másolása elemre.</span><span class="sxs-lookup"><span data-stu-id="74220-128">Click Copy day.</span></span>
    * <span data-ttu-id="74220-129">Másolja át a munkaidők definícióit hétfőről szerdára.</span><span class="sxs-lookup"><span data-stu-id="74220-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="74220-130">Válasszon egy lehetőséget a Befejező hétköznap mezőben.</span><span class="sxs-lookup"><span data-stu-id="74220-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="74220-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-131">Click OK.</span></span>
6. <span data-ttu-id="74220-132">Kattintson a Nap másolása elemre.</span><span class="sxs-lookup"><span data-stu-id="74220-132">Click Copy day.</span></span>
    * <span data-ttu-id="74220-133">Másolja át a munkaidők definícióit hétfőről csütörtökre.</span><span class="sxs-lookup"><span data-stu-id="74220-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="74220-134">Válasszon egy lehetőséget a Befejező hétköznap mezőben.</span><span class="sxs-lookup"><span data-stu-id="74220-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="74220-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-135">Click OK.</span></span>
9. <span data-ttu-id="74220-136">Kattintson a Nap másolása elemre.</span><span class="sxs-lookup"><span data-stu-id="74220-136">Click Copy day.</span></span>
    * <span data-ttu-id="74220-137">Másolja át a munkaidők definícióit hétfőről péntekre.</span><span class="sxs-lookup"><span data-stu-id="74220-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="74220-138">Válasszon egy lehetőséget a Befejező hétköznap mezőben.</span><span class="sxs-lookup"><span data-stu-id="74220-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="74220-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="74220-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="74220-140">Időközök meghatározása speciális műveletekhez</span><span class="sxs-lookup"><span data-stu-id="74220-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="74220-141">Bontsa ki a Péntek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="74220-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="74220-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="74220-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="74220-143">A Tulajdonság mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="74220-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="74220-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="74220-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="74220-145">A Tulajdonság mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="74220-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="74220-146">Hétvégek megjelölése zárt felvételhez</span><span class="sxs-lookup"><span data-stu-id="74220-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="74220-147">Bontsa ki a Szombat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="74220-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="74220-148">A Lezárt felvétel mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74220-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="74220-149">Bontsa ki a Vasárnap szakaszt.</span><span class="sxs-lookup"><span data-stu-id="74220-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="74220-150">A Lezárt felvétel mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74220-150">Select Yes in the Closed for pickup field.</span></span>


