---
title: Első lépések a tervezési optimalizálással
description: Ez a témakör bemutatja, hogyan kezdje el használni a tervezési optimalizáció funkciót.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
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
ms.openlocfilehash: ce1bbb18e9a448e84d001a4195421d2b0e4af5be
ms.sourcegitcommit: c0d37fdd70f3dec4605fdee6f981f84a49be9b9e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2020
ms.locfileid: "3339878"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="8c4d2-103">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="8c4d2-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8c4d2-104">A tervezés optimalizálása funkció jelenleg nem támogatja az összes olyan funkciót, amely a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba épített tervezési motorban rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="8c4d2-105">Ezért fontos, hogy meggyőződjön, hogy a tervezésoptimalizálásban jelenleg elérhető szolgáltatáskészlet kielégíti-e a követelményeket.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="8c4d2-106">Alapértelmezés szerint a Tervezés optimalizálása funkció nincs bekapcsolva a Dynamics Lifecycle Services (LCS) modulban.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="8c4d2-107">Ennek megfelelően lehetősége van arra, hogy az értékelést a bekapcsolás előtt végezze el.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="8c4d2-108">Végül a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management tervezési motorját.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="8c4d2-109">A tervezés optimalizálása előtt kifejezetten ajánljuk, hogy értékelje a tervezésoptimalizálás illeszkedési elemzésének eredményeit.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="8c4d2-110">További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="8c4d2-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="8c4d2-111">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="8c4d2-111">Availability</span></span>
<span data-ttu-id="8c4d2-112">A Tervezési optimalizálása jelenleg a következő Azure földrajzi területeken érhető el: Egyesült Államok, Kanada, Európa, Egyesült Királyság és Ausztrália.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="8c4d2-113">Ha egy másik földrajzi régióból kísérli meg telepíteni a bővítményt, akkor az LCS egy üzenetet jelenít meg, hogy ez a földrajzi hely nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="8c4d2-114">Ne feledje, hogy a Tervezés optimalizálása nem támogatott a Dynamics 365 Supply Chain Management helyszíni telepítései esetében.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="8c4d2-115">Licenckezelés</span><span class="sxs-lookup"><span data-stu-id="8c4d2-115">Licensing</span></span>

<span data-ttu-id="8c4d2-116">Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="8c4d2-117">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="8c4d2-117">Install the add-in</span></span>

<span data-ttu-id="8c4d2-118">A Tervezés optimalizálása modul használatához telepíteni kell a Tervezés optimalizálása bővítményt a következőhöz: Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="8c4d2-119">A bővítményt a LCS-projektből érheti el, és a Supply Chain Management felhasználói felületéről (UI) be lehet kapcsolni a tervezés optimalizálása funkcióját.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="8c4d2-120">A tervezésoptimalizálás követelménye egy 2. szintű vagy magasabb LCS-kompatibilis magas rendelkezésre állású környezet (nem OneBox környezet), a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="8c4d2-121">Ha OneBox- környezetbe próbálja meg telepíteni a bővítményt, akkor a telepítés nem fejeződik be, és a telepítést vissza kell vonni.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="8c4d2-122">Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="8c4d2-123">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="8c4d2-124">Görgessen le a **Környezeti bővítmények** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="8c4d2-125">Válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="8c4d2-126">Válassza a **Tervezés optimalizálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="8c4d2-127">Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="8c4d2-128">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-128">Select **Install**.</span></span>
1. <span data-ttu-id="8c4d2-129">A **Környezeti bővítmények** gyorslapon látnia kell, hogy a Tervezési optimalizálás telepítése folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="8c4d2-130">Néhány perc múlva a **Telepítés** felirat erre módosul: **Telepítve** (előfordulhat, hogy frissíteni kell az oldalt).</span><span class="sxs-lookup"><span data-stu-id="8c4d2-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="8c4d2-131">A telepítés befejezésekor készen áll a Tervezési optimalizálás funkció aktiválására a Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="8c4d2-132">A tervezésoptimalizálás integrációja</span><span class="sxs-lookup"><span data-stu-id="8c4d2-132">Planning Optimization integration</span></span>

<span data-ttu-id="8c4d2-133">Annak konfigurálásához, hogy a Tervezési optimalizálás bővítményt használja-e a rendszer az alaptervezéshez, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezési optimalizálás paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="8c4d2-134">Kapcsolat állapota</span><span class="sxs-lookup"><span data-stu-id="8c4d2-134">Connection status</span></span>

<span data-ttu-id="8c4d2-135">A kapcsolat állapota jelzi a kapcsolat aktuális állapotát a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="8c4d2-136">A következő táblázat mutatja a lehetséges értékeket.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="8c4d2-137">Kapcsolat állapota</span><span class="sxs-lookup"><span data-stu-id="8c4d2-137">Connection status</span></span> | <span data-ttu-id="8c4d2-138">Leírás</span><span class="sxs-lookup"><span data-stu-id="8c4d2-138">Description</span></span> | <span data-ttu-id="8c4d2-139">Használható a Tervezésoptimalizálás?</span><span class="sxs-lookup"><span data-stu-id="8c4d2-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="8c4d2-140">Csatlakoztatva</span><span class="sxs-lookup"><span data-stu-id="8c4d2-140">Connected</span></span> | <span data-ttu-id="8c4d2-141">A rendszer kapcsolatot létesített a Tervezésoptimalizálás és a Supply Chain Management között.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="8c4d2-142">Igen</span><span class="sxs-lookup"><span data-stu-id="8c4d2-142">Yes</span></span> |
| <span data-ttu-id="8c4d2-143">Kapcsolat engedélyezése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-143">Enabling connection</span></span> | <span data-ttu-id="8c4d2-144">Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat bekapcsolási kérelme.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="8c4d2-145">Nem</span><span class="sxs-lookup"><span data-stu-id="8c4d2-145">No</span></span> |
| <span data-ttu-id="8c4d2-146">Leválasztva</span><span class="sxs-lookup"><span data-stu-id="8c4d2-146">Disconnected</span></span> | <span data-ttu-id="8c4d2-147">Nincs kapcsolat a tervezés optimalizálása szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="8c4d2-148">A kapcsolat a következő témakörben leírtak szerint a LCS-ről kapcsolható be.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="8c4d2-149">Nem</span><span class="sxs-lookup"><span data-stu-id="8c4d2-149">No</span></span> |
| <span data-ttu-id="8c4d2-150">Kapcsolat letiltása</span><span class="sxs-lookup"><span data-stu-id="8c4d2-150">Disabling connection</span></span> | <span data-ttu-id="8c4d2-151">Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat kikapcsolási kérelme.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="8c4d2-152">Nem</span><span class="sxs-lookup"><span data-stu-id="8c4d2-152">No</span></span> |
| <span data-ttu-id="8c4d2-153">Állapot lekérése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-153">Getting status</span></span> | <span data-ttu-id="8c4d2-154">A rendszer a tervezés optimalizálása szolgáltatásból származó állapotadatokra várakozik.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="8c4d2-155">Nem</span><span class="sxs-lookup"><span data-stu-id="8c4d2-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="8c4d2-156">A Tervezésoptimalizálás beállítás használata</span><span class="sxs-lookup"><span data-stu-id="8c4d2-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="8c4d2-157">A **Tervezés optimalizálása használata** beállítás határozza meg, hogy melyik tervezési motor használható az alaptervezéshez:</span><span class="sxs-lookup"><span data-stu-id="8c4d2-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="8c4d2-158">**Igen** – a tervezésoptimalizálás az alaptervezéshez használatos.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="8c4d2-159">**Nem** – Az alaptervezéshez a Supply Chain Management beépített tervezési motorja használatos.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="8c4d2-160">Ha meglévő tervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, elindulnak, miközben a **Tervezésoptimalizálás használata** beállítás értéke **Igen**, a feladatok sikertelenek lesznek.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="8c4d2-161">Integráció a beállítással</span><span class="sxs-lookup"><span data-stu-id="8c4d2-161">Integration with the setup</span></span>

<span data-ttu-id="8c4d2-162">Ha a Tervezésoptimalizálás előzetes verziója be van kapcsolva, akkor az alaptervezést a rendszer a Tervezésoptimalizálás bővítménnyel végzi.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="8c4d2-163">Ebben az esetben az Alaptervezés eredményeit és funkcióit érinti a program.</span><span class="sxs-lookup"><span data-stu-id="8c4d2-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c4d2-164">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8c4d2-164">Additional resources</span></span>

[<span data-ttu-id="8c4d2-165">Az előzetes verzió feltételei és kikötései</span><span class="sxs-lookup"><span data-stu-id="8c4d2-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="8c4d2-166">Tervezési optimalizálás áttekintése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="8c4d2-167">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="8c4d2-168">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="8c4d2-169">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="8c4d2-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="8c4d2-170">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="8c4d2-170">Cancel a planning job</span></span>](cancel-planning-job.md)
