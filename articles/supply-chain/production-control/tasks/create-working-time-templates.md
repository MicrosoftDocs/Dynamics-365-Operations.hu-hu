---
title: Munkaidősablonok készítése
description: A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920929"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="2179f-103">Munkaidősablonok készítése</span><span class="sxs-lookup"><span data-stu-id="2179f-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2179f-104">A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="2179f-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="2179f-105">Ez az eljárás bemutatja, hogyan definiálhat munkaidősablonokat a munkaidő-ütemezési tulajdonságok segítségével a munkaidő-intervallumok kategorizálásához.</span><span class="sxs-lookup"><span data-stu-id="2179f-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="2179f-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="2179f-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="2179f-107">Ugorjon a **Munkaterületek > Erőforrás életciklusa kezelése** elemre.</span><span class="sxs-lookup"><span data-stu-id="2179f-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="2179f-108">Válassza a **Munkaidősablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="2179f-109">Munkaidősablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="2179f-109">Create working time template</span></span>

1. <span data-ttu-id="2179f-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-110">Select **New**.</span></span>
1. <span data-ttu-id="2179f-111">Írjon be egy értéket a **Munkidősablon** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2179f-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="2179f-112">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2179f-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="2179f-113">Bontsa ki a **Hétfő** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2179f-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="2179f-114">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-114">Select **Add**.</span></span>
1. <span data-ttu-id="2179f-115">A **Kezdés** mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="2179f-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="2179f-116">Adja meg az időt, amikor a munka reggel elkezdődik.</span><span class="sxs-lookup"><span data-stu-id="2179f-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="2179f-117">A **Befejezés** mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="2179f-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="2179f-118">Adja meg a dolgozók ebédszünetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="2179f-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="2179f-119">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-119">Select **Add**.</span></span>
1. <span data-ttu-id="2179f-120">A **Kezdés** mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="2179f-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="2179f-121">Adja meg, hogy mikor folytatódik a munka ebéd után.</span><span class="sxs-lookup"><span data-stu-id="2179f-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="2179f-122">A **Befejezés** mezőben adjon meg egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="2179f-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="2179f-123">A munkanap végének meghatározása.</span><span class="sxs-lookup"><span data-stu-id="2179f-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="2179f-124">Munkaidők átmásolása minden hétköznapra</span><span class="sxs-lookup"><span data-stu-id="2179f-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="2179f-125">Válassza a **Másolási nap** parancsot.</span><span class="sxs-lookup"><span data-stu-id="2179f-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="2179f-126">Másolja át a munkaidők definícióit hétfőről keddre.</span><span class="sxs-lookup"><span data-stu-id="2179f-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="2179f-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-127">Select **OK**.</span></span>
1. <span data-ttu-id="2179f-128">Válassza a **Másolási nap** parancsot.</span><span class="sxs-lookup"><span data-stu-id="2179f-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="2179f-129">Másolja át a munkaidők definícióit hétfőről szerdára.</span><span class="sxs-lookup"><span data-stu-id="2179f-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="2179f-130">Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2179f-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="2179f-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-131">Select **OK**.</span></span>
1. <span data-ttu-id="2179f-132">Válassza a **Másolási nap** parancsot.</span><span class="sxs-lookup"><span data-stu-id="2179f-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="2179f-133">Másolja át a munkaidők definícióit hétfőről csütörtökre.</span><span class="sxs-lookup"><span data-stu-id="2179f-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="2179f-134">Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2179f-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="2179f-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-135">Select **OK**.</span></span>
1. <span data-ttu-id="2179f-136">Válassza a **Másolási nap** parancsot.</span><span class="sxs-lookup"><span data-stu-id="2179f-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="2179f-137">Másolja át a munkaidők definícióit hétfőről péntekre.</span><span class="sxs-lookup"><span data-stu-id="2179f-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="2179f-138">Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2179f-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="2179f-139">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="2179f-140">Időközök meghatározása speciális műveletekhez</span><span class="sxs-lookup"><span data-stu-id="2179f-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="2179f-141">Bontsa ki a **Péntek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2179f-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="2179f-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2179f-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="2179f-143">A **Tulajdonság** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2179f-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="2179f-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2179f-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="2179f-145">A **Tulajdonság** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2179f-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="2179f-146">Hétvégek megjelölése zárt felvételhez</span><span class="sxs-lookup"><span data-stu-id="2179f-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="2179f-147">Bontsa ki a **Szombat** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2179f-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="2179f-148">A *Lezárt felvétel* mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="2179f-149">Bontsa ki a **Vasárnap** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2179f-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="2179f-150">A *Lezárt felvétel* mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2179f-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]