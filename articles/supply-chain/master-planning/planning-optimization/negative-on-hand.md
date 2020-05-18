---
title: Tervezés negatív tényleges készleten lévő mennyiségekkel
description: Ez a témakör azt mutatja be, hogy hogyan kezeli a program a negatív aktuális készletet a tervezés optimalizálása során.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 72367927a11879adffe68d7242d88f5cfab73e22
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323508"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="305b2-103">Tervezés negatív tényleges készleten lévő mennyiségekkel</span><span class="sxs-lookup"><span data-stu-id="305b2-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="305b2-104">Ha a rendszer negatív összesített tényleges mennyiséget mutat, akkor a tervezési motor a mennyiséget 0 (nulla) értékkel kezeli a túlszállítás elkerülésére.</span><span class="sxs-lookup"><span data-stu-id="305b2-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="305b2-105">Ez a funkció működése:</span><span class="sxs-lookup"><span data-stu-id="305b2-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="305b2-106">A tervezés optimalizálása funkció összesíti az aktuális készleten lévő mennyiségeket a fedezeti dimenziók legalacsonyabb szintjén.</span><span class="sxs-lookup"><span data-stu-id="305b2-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="305b2-107">(Ha például a *hely* nem fedezeti dimenzió, akkor a tervezés optimalizálása a *raktár* szintjén összesíti az aktuális készleten lévő mennyiségeket.)</span><span class="sxs-lookup"><span data-stu-id="305b2-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="305b2-108">Ha negatív a fedezeti dimenziók legalacsonyabb szintjén levő összesített aktuális mennyiség, a rendszer azt feltételezi, hogy az aktuális készlet mennyisége valóban 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="305b2-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="305b2-109">A tervezési rendszer csak akkor lehet pontos, mint a bemeneti adat.</span><span class="sxs-lookup"><span data-stu-id="305b2-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="305b2-110">Ha a bemeneti adatok pontatlanok, akkor a negatív tényleges készlet rekordok azt jelzik, hogy a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban lévő készlet adatai nincsenek harmóniában a valós világgal.</span><span class="sxs-lookup"><span data-stu-id="305b2-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="305b2-111">Ezért a tervezés eredménye hibás lesz.</span><span class="sxs-lookup"><span data-stu-id="305b2-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="305b2-112">A pontos tervezési eredmény érdekében minimalizálni kell azokat a rekordokat, amelyek negatív aktuális mennyiséget jelenítenek meg.</span><span class="sxs-lookup"><span data-stu-id="305b2-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="305b2-113">1. példa</span><span class="sxs-lookup"><span data-stu-id="305b2-113">Example 1</span></span>

<span data-ttu-id="305b2-114">A 13. raktár konfigurálása a következő módon történik:</span><span class="sxs-lookup"><span data-stu-id="305b2-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="305b2-115">**Fedezeti kód:** Min./Max.</span><span class="sxs-lookup"><span data-stu-id="305b2-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="305b2-116">**Minimum:** 15 darab (db)</span><span class="sxs-lookup"><span data-stu-id="305b2-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="305b2-117">**Maximum:** 25 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="305b2-118">A fedezeti dimenziók legalacsonyabb szintje a *raktár*, és a következő aktuális mennyiségeket rögzíti a rendszer a *hely* szintjén:</span><span class="sxs-lookup"><span data-stu-id="305b2-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="305b2-119">**1. telephely, 13. raktár, 1. hely:** 20 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="305b2-120">**1. telephely, 13. raktár, 2. hely:** &minus;8 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="305b2-121">Ennek megfelelően a 13. raktár összesített tényleges mennyisége 12 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="305b2-122">(= 20 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-122">(= 20 pcs.</span></span> <span data-ttu-id="305b2-123">&minus; 8 db.).</span><span class="sxs-lookup"><span data-stu-id="305b2-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="305b2-124">Ebben az esetben a tervezési motor az összesített 12 darabos aktuális készletet használja</span><span class="sxs-lookup"><span data-stu-id="305b2-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="305b2-125">a 13. raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="305b2-125">for warehouse 13.</span></span>

<span data-ttu-id="305b2-126">Az eredmény 13 darabból álló tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="305b2-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="305b2-127">(= 25 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-127">(= 25 pcs.</span></span> <span data-ttu-id="305b2-128">&minus; 12 db.) a 13. raktár újratöltése 12 darabról</span><span class="sxs-lookup"><span data-stu-id="305b2-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="305b2-129">25 darabra.</span><span class="sxs-lookup"><span data-stu-id="305b2-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="305b2-130">2. példa</span><span class="sxs-lookup"><span data-stu-id="305b2-130">Example 2</span></span>

<span data-ttu-id="305b2-131">A 13. raktár konfigurálása a következő módon történik:</span><span class="sxs-lookup"><span data-stu-id="305b2-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="305b2-132">**Fedezeti kód:** Min./Max.</span><span class="sxs-lookup"><span data-stu-id="305b2-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="305b2-133">**Minimum:** 15 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="305b2-134">**Maximum:** 25 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="305b2-135">A fedezeti dimenziók legalacsonyabb szintje a *raktár*, és a következő aktuális mennyiségeket rögzíti a rendszer a *hely* szintjén:</span><span class="sxs-lookup"><span data-stu-id="305b2-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="305b2-136">**1. telephely, 13. raktár, 1. hely:** 4 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="305b2-137">**1. telephely, 13. raktár, 2. hely:** &minus;8 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="305b2-138">Ennek megfelelően a 13. raktár összesített tényleges mennyisége &minus;4 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="305b2-139">(= 4 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-139">(= 4 pcs.</span></span> <span data-ttu-id="305b2-140">&minus; 8 db.).</span><span class="sxs-lookup"><span data-stu-id="305b2-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="305b2-141">Azaz kevesebb, mint 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="305b2-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="305b2-142">Ebben az esetben a tervezési motor feltételezi, hogy a 13. raktár aktuális készlete 0 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="305b2-143">&minus;4 db helyett.</span><span class="sxs-lookup"><span data-stu-id="305b2-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="305b2-144">Az eredmény 25 darabból álló tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="305b2-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="305b2-145">(= 25 db.</span><span class="sxs-lookup"><span data-stu-id="305b2-145">(= 25 pcs.</span></span> <span data-ttu-id="305b2-146">&minus; 0 db.) a 13. raktár újratöltése 0 darabról</span><span class="sxs-lookup"><span data-stu-id="305b2-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="305b2-147">25 darabra.</span><span class="sxs-lookup"><span data-stu-id="305b2-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="305b2-148">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="305b2-148">Related resources</span></span>

[<span data-ttu-id="305b2-149">Tervezési optimalizálás áttekintése</span><span class="sxs-lookup"><span data-stu-id="305b2-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="305b2-150">Tervezési optimalizálás indítása</span><span class="sxs-lookup"><span data-stu-id="305b2-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="305b2-151">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="305b2-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="305b2-152">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="305b2-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="305b2-153">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="305b2-153">Cancel a planning job</span></span>](cancel-planning-job.md)
