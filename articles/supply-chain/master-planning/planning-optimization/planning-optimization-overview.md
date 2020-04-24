---
title: Tervezés optimalizálása – áttekintés
description: Ez a témakör áttekintést ad a Tervezésoptimalizálása funkcióiról.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
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
ms.openlocfilehash: f88ee8067fdd816ba6890ee28bafe8fa4d3b3ac5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208731"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="152e1-103">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="152e1-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="152e1-104">A Microsoft Dynamics 365 Supply Chain Management Tervezésoptimalizálási bővítménye lehetővé teszi, hogy az alaptervezési számítás a Dynamics 365 Supply Chain Management szolgáltatáson és a kapcsolódó SQL-adatbázison kívül történjen.</span><span class="sxs-lookup"><span data-stu-id="152e1-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="152e1-105">A tervezésoptimalizálás funkcióhoz társított előnyök között szerepel a továbbfejlesztett teljesítmény és az SQL-adatbázisra tett minimális hatás az Alaptervezés futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="152e1-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="152e1-106">A gyors tervezési futtatások a nyitvatartási idő alatt is megtehetők, így a tervezők azonnal reagálni tudnak a igényre vagy a paraméterek változásaira.</span><span class="sxs-lookup"><span data-stu-id="152e1-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="152e1-107">A Tervezésoptimalizálás funkció használatához telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) projektjéből a Tervezésoptimalizálás bővítményt, majd be kell kapcsolni a Tervezésoptimalizálás funkciót a Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="152e1-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="152e1-108">További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="152e1-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="152e1-109">A következő ábra bemutatja, hogy milyen előnyökkel jár a Tervezésoptimalizálás a nyitvatartási órákban.</span><span class="sxs-lookup"><span data-stu-id="152e1-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![A Tervezésoptimalizálás irodai órákban történő futtatásának előnyei](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="152e1-111">Javított teljesítmény</span><span class="sxs-lookup"><span data-stu-id="152e1-111">Improved performance</span></span>

<span data-ttu-id="152e1-112">A Tervezésoptimalizálás a hosszú távú alapterveket is magában foglaló esetekben használható.</span><span class="sxs-lookup"><span data-stu-id="152e1-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="152e1-113">Ez kifejezetten nagyon gyors számításokhoz van tervezve, amelyek nagy mennyiségű adatot érintenek.</span><span class="sxs-lookup"><span data-stu-id="152e1-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="152e1-114">Mivel a program a tetszőlegesen méretezhető multibérlő szolgáltatásként épült, több példány együtt dolgozhat egyidejűleg a terv kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="152e1-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="152e1-115">Ezenkívül a tervezési szolgáltatás eltávolítja az alaptervezés terhét a rendszerből, és olyan adatfolyamot dolgozik, amely minimalizálja a kiszolgáló terhelését.</span><span class="sxs-lookup"><span data-stu-id="152e1-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="152e1-116">A Tervezésoptimalizálás a következő célok elérése érdekében használható:</span><span class="sxs-lookup"><span data-stu-id="152e1-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="152e1-117">A tervezési teljesítmény javítása a rövidebb futásidőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="152e1-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="152e1-118">Az Alaptervezés futtatása közben a többi folyamatra gyakorolt hatás csökkentése.</span><span class="sxs-lookup"><span data-stu-id="152e1-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="152e1-119">Gyakrabban kell tervezni a tervezést.</span><span class="sxs-lookup"><span data-stu-id="152e1-119">Do more frequent planning runs.</span></span> <span data-ttu-id="152e1-120">(Nem korlátozódik a napi futtatásra.)</span><span class="sxs-lookup"><span data-stu-id="152e1-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="152e1-121">Győződjön meg arról, hogy a jövőbeli üzleti növekedés nem terheli meg a tervezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="152e1-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="152e1-122">Architektúra és az adatforgalom</span><span class="sxs-lookup"><span data-stu-id="152e1-122">Architecture and data flow</span></span>

<span data-ttu-id="152e1-123">Amikor a Tervezésoptimalizálás bővítményt telepíti a LCS-ből, létrejön egy biztonságos kapcsolat a Tervezésoptimalizálás szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="152e1-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="152e1-124">A szolgáltatás ugyanabban az adatközpontként megadott országban vagy területen található, mint a kapcsolódó Supply Chain Management példány.</span><span class="sxs-lookup"><span data-stu-id="152e1-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="152e1-125">A Tervezésoptimalizálás beállítása után az Alaptervezés futtatásakor az alapadatok és a tranzakciós adatok a Supply Chain Management szolgáltatásból érkeznek a Tervezésoptimalizálás szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="152e1-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="152e1-126">Ha eltávolítja a Tervezésoptimalizálás bővítményt, akkor a program eltávolítja a Tervezésoptimalizálás szolgáltatással kapcsolatos összes adatot.</span><span class="sxs-lookup"><span data-stu-id="152e1-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="152e1-127">A regeneráláshoz szükséges magas szintű adatfolyamok</span><span class="sxs-lookup"><span data-stu-id="152e1-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="152e1-128">A Supply Chain Management kliens egy olyan jelet küld, amely a Tervezésoptimalizálás kéri a tervezési futtatást.</span><span class="sxs-lookup"><span data-stu-id="152e1-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="152e1-129">A Tervezésoptimalizálás a szükséges adatokat a beépített összekötőn keresztül kéri.</span><span class="sxs-lookup"><span data-stu-id="152e1-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="152e1-130">Az SQL-adatbázis elküldi a Tervezésoptimalizálásnak a kért információkat a beállítással, alap- és tranzakciós adatokkal kapcsolatban az összekötőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="152e1-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="152e1-131">Az összekötő lefordítja az információkat a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között.</span><span class="sxs-lookup"><span data-stu-id="152e1-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="152e1-132">ATervezésoptimalizálás szolgáltatás a memóriában a tervezéssel kapcsolatos adatokat tárolja, és a szükséges számításokat.</span><span class="sxs-lookup"><span data-stu-id="152e1-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="152e1-133">A tervezési eredményt a program az összekötőn keresztül küldi el a Supply Chain Management adatbázisnak.</span><span class="sxs-lookup"><span data-stu-id="152e1-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="152e1-134">Az eredmények között szerepelnek például a tervezett rendelések és a rögzített adatok.</span><span class="sxs-lookup"><span data-stu-id="152e1-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="152e1-135">A Tervezésoptimalizálás jel küldésével jelzi a Supply Chain Management számára, hogy a tervezés futtatása befejeződött.</span><span class="sxs-lookup"><span data-stu-id="152e1-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="152e1-136">Ezenkívül a megfelelő üzeneteket és figyelmeztetéseket is elküldi.</span><span class="sxs-lookup"><span data-stu-id="152e1-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="152e1-137">A következő ábra ábrázolja az adatok áramlását.</span><span class="sxs-lookup"><span data-stu-id="152e1-137">The following illustration shows the data flow.</span></span>

![Adatforgalom a regenerálási futtatásokhoz](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="152e1-139">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="152e1-139">Related resources</span></span>

[<span data-ttu-id="152e1-140">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="152e1-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="152e1-141">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="152e1-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="152e1-142">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="152e1-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="152e1-143">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="152e1-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="152e1-144">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="152e1-144">Cancel a planning job</span></span>](cancel-planning-job.md)
