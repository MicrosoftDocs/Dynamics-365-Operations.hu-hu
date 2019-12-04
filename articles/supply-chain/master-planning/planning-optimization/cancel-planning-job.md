---
title: Tervezési feladat érvénytelenítése
description: Ez a témakör azt mutatja be, hogyan lehet érvényteleníteni egy olyan aktív tervezési feladatot, amely a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
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
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773976"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="17deb-103">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="17deb-103">Cancel a planning job</span></span>

<span data-ttu-id="17deb-104">A Microsoft Dynamics 365 Supply Chain Management rendszerben érvényteleníthetők az olyan aktív tervezési feladatok, amelyek a Tervezés optimalizálása funkciót használják.</span><span class="sxs-lookup"><span data-stu-id="17deb-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="17deb-105">Aktív tervezési feladat érvénytelenítéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="17deb-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="17deb-106">Csak egy aktív feladat érvényteleníthető.</span><span class="sxs-lookup"><span data-stu-id="17deb-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="17deb-107">Lépjen az **Alaptervezés \> Beállítás \> Tervek** részre.</span><span class="sxs-lookup"><span data-stu-id="17deb-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="17deb-108">Válassza ki a tervezés futtatásához megfelelő tervet.</span><span class="sxs-lookup"><span data-stu-id="17deb-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="17deb-109">Válassza az **Előzmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17deb-109">Select **History**.</span></span>
4. <span data-ttu-id="17deb-110">Válassza ki az érvényteleníteni kívánt tervezési feladatot.</span><span class="sxs-lookup"><span data-stu-id="17deb-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="17deb-111">Válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17deb-111">Select **Cancel**.</span></span>

<span data-ttu-id="17deb-112">A feladat állapota mindaddig **Megszakítás** lesz, amíg a Tervezés optimalizálása szolgáltatás meg nem erősíti, hogy a feladat érvénytelenítve lett.</span><span class="sxs-lookup"><span data-stu-id="17deb-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="17deb-113">Ezt követően az állapot **Megszakítva** lesz.</span><span class="sxs-lookup"><span data-stu-id="17deb-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="17deb-114">Az állapot változásainak megjelenítéséhez a **Frissítés** gombra kattintva frissíteni kell az oldalt.</span><span class="sxs-lookup"><span data-stu-id="17deb-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="17deb-115">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="17deb-115">Related resources</span></span>

[<span data-ttu-id="17deb-116">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="17deb-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="17deb-117">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="17deb-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="17deb-118">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="17deb-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="17deb-119">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="17deb-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="17deb-120">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="17deb-120">Apply filters to a plan</span></span>](plan-filters.md)
