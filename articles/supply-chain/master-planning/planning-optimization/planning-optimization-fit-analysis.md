---
title: A tervezésoptimalizálása illeszkedési elemzése
description: Ez a témakör azt mutatja be, hogyan lehet ellenőrizni az aktuális beállításokat és adatokat a Tervezésoptimalizálás funkció szolgáltatásaival szemben.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
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
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773974"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="69858-103">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="69858-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="69858-104">Ha szeretné megtekinteni, hogy az aktuális beállítások és adatok kompatibilisek-e a tervezésoptimalizálás funkcióval, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezésoptimalizálás illeszkedési elemzése** lehetőséget, majd az **Elemzés futtatása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="69858-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="69858-105">Ha az elemzés bármilyen következetlenséget talál, akkor ugyanazon a lapon szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="69858-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="69858-106">(Az elemzés néhány percet is igénybe vehet.)</span><span class="sxs-lookup"><span data-stu-id="69858-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="69858-107">Ha találhatók következetlenségek, akkor a tervezésoptimalizálása továbbra is használható.</span><span class="sxs-lookup"><span data-stu-id="69858-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="69858-108">Az illeszkedési elemzés eredményei csak azokat a helyeket jelenítik meg, ahol a tervezési szolgáltatás nem tiszteli az aktuális beállításokat.</span><span class="sxs-lookup"><span data-stu-id="69858-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="69858-109">Más szóval azokat a helyeket jelenítik meg, ahol bizonyos folyamatok figyelmen kívül lehetnek hagyva, vagy esetleg nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="69858-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="69858-110">Elemzési eredmények: 1. példa</span><span class="sxs-lookup"><span data-stu-id="69858-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="69858-111">**Funkció:** Termelés</span><span class="sxs-lookup"><span data-stu-id="69858-111">**Feature:** Production</span></span>
- <span data-ttu-id="69858-112">**Hiba:** Nullánál nagyobb BOM-szinttel rendelkező cikkek: 56</span><span class="sxs-lookup"><span data-stu-id="69858-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="69858-113">**Magyarázat:** Az illeszkedési elemzés 56 olyan cikket talál, amelynél a termeléshez anyagjegyzéket (BOM) állítottak be.</span><span class="sxs-lookup"><span data-stu-id="69858-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="69858-114">Mivel a tervezésoptimalizálás modul jelenlegi verziója nem támogatja a termelést, a tervezésoptimalizálás a tervezett termelési rendelések helyett tervezett beszerzési rendeléseket fog generálni.</span><span class="sxs-lookup"><span data-stu-id="69858-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="69858-115">Emellett figyelmeztetés jelenik meg, amely felsorolja az érintett cikkeket.</span><span class="sxs-lookup"><span data-stu-id="69858-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="69858-116">Elemzési eredmények: 2. példa</span><span class="sxs-lookup"><span data-stu-id="69858-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="69858-117">**Funkció:** műveletek</span><span class="sxs-lookup"><span data-stu-id="69858-117">**Feature:** Actions</span></span>
- <span data-ttu-id="69858-118">**Probléma:** Fedezeti csoportok, ahol műveletek számítása engedélyezett: 6</span><span class="sxs-lookup"><span data-stu-id="69858-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="69858-119">**Magyarázat:** Az illeszkedési elemzés hat olyan fedezeti csoportot talált, ahol a műveletszámítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="69858-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="69858-120">Mivel a tervezésoptimalizálás jelenlegi verziója nem támogatja a műveleteket, az Alaptervezés során nem jönnek létre műveletek.</span><span class="sxs-lookup"><span data-stu-id="69858-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="69858-121">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="69858-121">Related resources</span></span>

[<span data-ttu-id="69858-122">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="69858-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="69858-123">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="69858-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="69858-124">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="69858-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="69858-125">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="69858-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="69858-126">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="69858-126">Cancel a planning job</span></span>](cancel-planning-job.md)
