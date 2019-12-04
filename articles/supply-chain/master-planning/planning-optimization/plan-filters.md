---
title: Szűrők alkalmazása egy tervre
description: Ez a témakör azt mutatja be, hogyan lehet szűrőket használni egy terven, amikor a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ff9c9f875368fcc4dd62b9c188d489e20a5c7960
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773975"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="cad56-103">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="cad56-103">Apply filters to a plan</span></span>

<span data-ttu-id="cad56-104">A tervezés optimalizálása funkció használata esetén szűrőket alkalmazhat a tervre.</span><span class="sxs-lookup"><span data-stu-id="cad56-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="cad56-105">A terv szűrője mindig az Alaptervezés futtatásakor lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="cad56-105">The plan filter will always be applied during a master planning run.</span></span> <span data-ttu-id="cad56-106">A tervszűrő akkor hasznos, ha egy tervet egy adott cikkcsoportra szeretné korlátozni, és szeretne meggyőződni róla, hogy a létrejövő Alaptervezés részeként nem szerepelnek más cikkek.</span><span class="sxs-lookup"><span data-stu-id="cad56-106">A plan filter is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="cad56-107">Ha a tervszűrőt alkalmazta, és az alaptervezés futtatása során a futásidejű szűrő is alkalmazva van, akkor a tervezési futtatásban csak a két szűrő metszete szerepel.</span><span class="sxs-lookup"><span data-stu-id="cad56-107">If a plan filter is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="cad56-108">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="cad56-108">Example scenario</span></span>

<span data-ttu-id="cad56-109">Az A, B és C cikkeket tartalmazó tervszűrő van beállítva. Az alaptervezés-futásokat lefuttatják ugyanerre a tervre, de más futásidejű szűrőket alkalmaznak:</span><span class="sxs-lookup"><span data-stu-id="cad56-109">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="cad56-110">**A D cikket tartalmazó futásidejű-szűrő:** Nincsenek tervezett cikkek, mert nincs közös metszete a tervszűrőnek és a futásidejű szűrőnek.</span><span class="sxs-lookup"><span data-stu-id="cad56-110">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="cad56-111">**Futásidejű szűrő, amely tartalmazza az A és D elemet**: csak az A elem szerepel a tervezés futtatásakor, mivel a D-es elem nem része a terv szűrőnek.</span><span class="sxs-lookup"><span data-stu-id="cad56-111">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="cad56-112">**Futásidejű szűrő, amely tartalmazza a B elemet**: csak a B elem szerepel a tervezés futtatásakor, és megmarad a korábbi tervezés kimeneteként az A elem is.</span><span class="sxs-lookup"><span data-stu-id="cad56-112">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="cad56-113">**Az összes cikket tartalmazó futásidejű szűrő (üres szűrő)** : az A, a A és a C cikkek szerepelnek a tervezés futtatásakor, és korábbi tervezési kimenet A és B eleme felülíródik.</span><span class="sxs-lookup"><span data-stu-id="cad56-113">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="cad56-114">Lehetőleg ne állítson be tervszűrőt olyan terven, amelyet az **Alaptervezés paraméterei** oldalon **Aktuális dinamikus alaptervként** állított be.</span><span class="sxs-lookup"><span data-stu-id="cad56-114">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="cad56-115">Ellenkező esetben a rendszer a szűrt cikkekre korlátozza a dinamikus alapterv funkcióját.</span><span class="sxs-lookup"><span data-stu-id="cad56-115">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="cad56-116">Ha például a nettó követelmények olyan cikkeknél frissülnek, amelyek nem részei a tervszűrőnek, akkor nem jön létre eredmény.</span><span class="sxs-lookup"><span data-stu-id="cad56-116">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="cad56-117">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="cad56-117">Related resources</span></span>

[<span data-ttu-id="cad56-118">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="cad56-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="cad56-119">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="cad56-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="cad56-120">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="cad56-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="cad56-121">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="cad56-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="cad56-122">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="cad56-122">Cancel a planning job</span></span>](cancel-planning-job.md)
