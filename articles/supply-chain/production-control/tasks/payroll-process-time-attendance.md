--- 
title: "Munkaidő és jelenlét bérlistafolyamatának engedélyezése"
description: "Ez az eljárás bemutatja, hogyan lehet engedélyezni a munkaidő és jelenlét bérlistafolyamatát."
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 22ce633f65847f10fbe507b71bfc2bb33f595501
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="727be-103">Munkaidő és jelenlét bérlistafolyamatának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="727be-103">Enable the payroll process for time and attendance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="727be-104">Ez az eljárás bemutatja, hogyan lehet engedélyezni a munkaidő és jelenlét bérlistafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="727be-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="727be-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="727be-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="727be-106">Új fizetési típus létrehozása kapcsolódó díjalappal</span><span class="sxs-lookup"><span data-stu-id="727be-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="727be-107">Idő és jelenlét > Beállítás > Bérlista > Fizetési típusok</span><span class="sxs-lookup"><span data-stu-id="727be-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="727be-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="727be-108">Click New.</span></span>
3. <span data-ttu-id="727be-109">Érték beírása a Fizetési típus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="727be-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="727be-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="727be-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="727be-111">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="727be-111">Click Save.</span></span>
6. <span data-ttu-id="727be-112">Kattintson a Díjazásokra.</span><span class="sxs-lookup"><span data-stu-id="727be-112">Click Rates.</span></span>
    * <span data-ttu-id="727be-113">A kifizetési típusok különböző díjait meghatározott időintervallumokhoz lehet beállítani, és az egyes alkalmazottakhoz különböző díjazást lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="727be-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="727be-114">Nem mindig szükséges a díjakat létrehozni a kifizetési típusokhoz idő és jelenlét tekintetében.</span><span class="sxs-lookup"><span data-stu-id="727be-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="727be-115">Ez az adat már szerepelhet az alkalmazotti bérek létrehozásához használt bérszámfejtő rendszerben.</span><span class="sxs-lookup"><span data-stu-id="727be-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="727be-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="727be-116">Click New.</span></span>
8. <span data-ttu-id="727be-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="727be-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="727be-118">Adjon meg egy számot a Díjazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="727be-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="727be-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="727be-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="727be-120">Fizetési megállapodás létrehozása</span><span class="sxs-lookup"><span data-stu-id="727be-120">Create a pay agreement</span></span>
1. <span data-ttu-id="727be-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="727be-121">Close the page.</span></span>
2. <span data-ttu-id="727be-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="727be-122">Close the page.</span></span>
3. <span data-ttu-id="727be-123">Ugrás a Fizetési megállapodásokra.</span><span class="sxs-lookup"><span data-stu-id="727be-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="727be-124">Idő és jelenlét > Beállítás > Kifizetési megállapodások</span><span class="sxs-lookup"><span data-stu-id="727be-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="727be-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="727be-125">Click New.</span></span>
5. <span data-ttu-id="727be-126">Érték beírása a Fizetési megállapodás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="727be-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="727be-127">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="727be-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="727be-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="727be-128">Click Save.</span></span>
8. <span data-ttu-id="727be-129">Kattintson a szerződéssorokra.</span><span class="sxs-lookup"><span data-stu-id="727be-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="727be-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="727be-130">Click New.</span></span>
10. <span data-ttu-id="727be-131">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="727be-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="727be-132">A Profiltípus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="727be-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="727be-133">A Kifizetési típus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="727be-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="727be-134">Fizetési megállapodás beállítása dolgozói idő és nyilvántartás alapján</span><span class="sxs-lookup"><span data-stu-id="727be-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="727be-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="727be-135">Close the page.</span></span>
2. <span data-ttu-id="727be-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="727be-136">Close the page.</span></span>
3. <span data-ttu-id="727be-137">Ugrás az Időnyilvántartás-dolgozókra.</span><span class="sxs-lookup"><span data-stu-id="727be-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="727be-138">Idő és jelenlét > Beállítás > Munkaidő-nyilvántartási dolgozók</span><span class="sxs-lookup"><span data-stu-id="727be-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="727be-139">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="727be-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="727be-140">Kattintson a Foglalkoztatás lapra.</span><span class="sxs-lookup"><span data-stu-id="727be-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="727be-141">Bontsa ki az Időnyilvántartás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="727be-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="727be-142">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="727be-142">Click Edit.</span></span>
8. <span data-ttu-id="727be-143">A Fizetési megállapodás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="727be-143">In the Pay agreement field, enter or select a value.</span></span>

