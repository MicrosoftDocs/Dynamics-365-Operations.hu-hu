---
title: Szűrők alkalmazása egy tervre
description: Ez a témakör azt mutatja be, hogyan lehet szűrőket használni egy terven, amikor a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 73e4a045ff5a9912b898a7115d3d8f530846ebdd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209789"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="c4be4-103">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="c4be4-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4be4-104">A tervezés optimalizálása funkció használata esetén szűrőket alkalmazhat a tervre.</span><span class="sxs-lookup"><span data-stu-id="c4be4-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="c4be4-105">A **Tervszűrő** mindig az alaptervezés futtatásakor lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="c4be4-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="c4be4-106">A **Tervszűrő** akkor hasznos, ha egy tervet egy adott cikkcsoportra szeretné korlátozni, és szeretne meggyőződni róla, hogy a létrejövő alaptervezés részeként nem szerepelnek más cikkek.</span><span class="sxs-lookup"><span data-stu-id="c4be4-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="c4be4-107">Ha a **tervszűrőt** alkalmazta, és az alaptervezés futtatása során a futásidejű szűrő is alkalmazva van, akkor a tervezési futtatásban csak a két szűrő metszete szerepel.</span><span class="sxs-lookup"><span data-stu-id="c4be4-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="c4be4-108">A **tervszűrőt** a Tervezési optimalizálás során az **alaptervekből** is el lehet érni.</span><span class="sxs-lookup"><span data-stu-id="c4be4-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c4be4-109">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="c4be4-109">Example scenario</span></span>

<span data-ttu-id="c4be4-110">Az A, B és C cikkeket tartalmazó tervszűrő van beállítva. Az alaptervezés-futásokat lefuttatják ugyanerre a tervre, de más futásidejű szűrőket alkalmaznak:</span><span class="sxs-lookup"><span data-stu-id="c4be4-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="c4be4-111">**A D cikket tartalmazó futásidejű-szűrő:** Nincsenek tervezett cikkek, mert nincs közös metszete a tervszűrőnek és a futásidejű szűrőnek.</span><span class="sxs-lookup"><span data-stu-id="c4be4-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="c4be4-112">**Futásidejű szűrő, amely tartalmazza az A és D elemet**: csak az A elem szerepel a tervezés futtatásakor, mivel a D-es elem nem része a terv szűrőnek.</span><span class="sxs-lookup"><span data-stu-id="c4be4-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="c4be4-113">**Futásidejű szűrő, amely tartalmazza a B elemet**: csak a B elem szerepel a tervezés futtatásakor, és megmarad a korábbi tervezés kimeneteként az A elem is.</span><span class="sxs-lookup"><span data-stu-id="c4be4-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="c4be4-114">**Az összes cikket tartalmazó futásidejű szűrő (üres szűrő)** : az A, a A és a C cikkek szerepelnek a tervezés futtatásakor, és korábbi tervezési kimenet A és B eleme felülíródik.</span><span class="sxs-lookup"><span data-stu-id="c4be4-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="c4be4-115">Lehetőleg ne állítson be tervszűrőt olyan terven, amelyet az **Alaptervezés paraméterei** oldalon **Aktuális dinamikus alaptervként** állított be.</span><span class="sxs-lookup"><span data-stu-id="c4be4-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="c4be4-116">Ellenkező esetben a rendszer a szűrt cikkekre korlátozza a dinamikus alapterv funkcióját.</span><span class="sxs-lookup"><span data-stu-id="c4be4-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="c4be4-117">Ha például a nettó követelmények olyan cikkeknél frissülnek, amelyek nem részei a tervszűrőnek, akkor nem jön létre eredmény.</span><span class="sxs-lookup"><span data-stu-id="c4be4-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c4be4-118">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4be4-118">Related resources</span></span>

[<span data-ttu-id="c4be4-119">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="c4be4-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="c4be4-120">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="c4be4-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="c4be4-121">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="c4be4-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="c4be4-122">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="c4be4-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="c4be4-123">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="c4be4-123">Cancel a planning job</span></span>](cancel-planning-job.md)
