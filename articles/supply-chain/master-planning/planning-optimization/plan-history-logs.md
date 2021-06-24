---
title: Tervelőzmények és tervezési naplók megtekintése
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni a tervezés optimalizálása funkció által kezdeményezett tervezési feladatok előzményeit.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187247"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="b9ab8-103">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="b9ab8-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9ab8-104">Ez a témakör azt mutatja be, hogyan lehet megtekinteni a tervezés optimalizálása funkció által kezdeményezett tervezési feladatok előzményeit a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b9ab8-105">A terv előzményeinek megtekintéséhez nyissa meg a tervet az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervek** pontban, majd válassza ki az **Előzmények** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="b9ab8-106">Az előzményben felsorolva láthatók a kiválasztott tervekhez tartozó feladatok.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="b9ab8-107">A lista tartalmazza a befejezett és az aktív feladatokat.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="b9ab8-108">A Tervezési optimalizálási alaptervezés feladatelőzményei csak alaptervenként legfeljebb 60 rekordot tartnak fent.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="b9ab8-109">Amikor új alaptervezési számítást futtat, annak a tervnek a legkorábbi előzményrekordja törlődik.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="b9ab8-110">A feladatok kezdési időpontjának és állapotának megtekintésén kívül az adott feladatra vonatkozó naplót is megtekintheti.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="b9ab8-111">A napló további információkat és figyelmeztetéseket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="b9ab8-112">Nem minden feladatnak van naplója.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-112">Not all jobs have a log.</span></span> <span data-ttu-id="b9ab8-113">A feladathoz tartozó napló megtekintéséhez válassza ki a **Napló** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="b9ab8-114">A naplóbejegyzések csak a munka befejezése után 30 napig tárolódnak, azokat automatikusan törli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="b9ab8-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b9ab8-115">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="b9ab8-115">Related resources</span></span>

- [<span data-ttu-id="b9ab8-116">Tervezési optimalizálás áttekintése</span><span class="sxs-lookup"><span data-stu-id="b9ab8-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="b9ab8-117">Tervezési optimalizálás kezdő lépései</span><span class="sxs-lookup"><span data-stu-id="b9ab8-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="b9ab8-118">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="b9ab8-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="b9ab8-119">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="b9ab8-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="b9ab8-120">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="b9ab8-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]