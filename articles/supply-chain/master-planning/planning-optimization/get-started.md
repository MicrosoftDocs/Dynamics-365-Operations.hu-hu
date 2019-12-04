---
title: Első lépések a tervezési optimalizálással
description: Ez a témakör bemutatja, hogyan kezdje el használni a tervezési optimalizáció funkciót.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
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
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773971"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="cf20f-103">Első lépések a tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="cf20f-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="cf20f-104">A tervezés optimalizálása funkció jelenleg nem támogatja az összes olyan funkciót, amely a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba épített tervezési motorban rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="cf20f-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="cf20f-105">Ezért fontos, hogy meggyőződjön, hogy a tervezésoptimalizálásban jelenleg elérhető szolgáltatáskészlet kielégíti-e a követelményeket.</span><span class="sxs-lookup"><span data-stu-id="cf20f-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="cf20f-106">Alapértelmezés szerint a Tervezés optimalizálása funkció nincs bekapcsolva a Dynamics Lifecycle Services (LCS) modulban.</span><span class="sxs-lookup"><span data-stu-id="cf20f-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="cf20f-107">Ennek megfelelően lehetősége van arra, hogy az értékelést a bekapcsolás előtt végezze el.</span><span class="sxs-lookup"><span data-stu-id="cf20f-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="cf20f-108">Végül a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management tervezési motorját.</span><span class="sxs-lookup"><span data-stu-id="cf20f-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="cf20f-109">A tervezés optimalizálása előtt kifejezetten ajánljuk, hogy értékelje a tervezésoptimalizálás illeszkedési elemzésének eredményeit.</span><span class="sxs-lookup"><span data-stu-id="cf20f-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="cf20f-110">További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="cf20f-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="cf20f-111">Licenckezelés</span><span class="sxs-lookup"><span data-stu-id="cf20f-111">Licensing</span></span>

<span data-ttu-id="cf20f-112">Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.</span><span class="sxs-lookup"><span data-stu-id="cf20f-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="cf20f-113">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="cf20f-113">Install the add-in</span></span>

<span data-ttu-id="cf20f-114">A Tervezés optimalizálása modul használatához telepíteni kell a Tervezés optimalizálása bővítményt a következőhöz: Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cf20f-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="cf20f-115">A bővítményt a LCS-projektből érheti el, és a Supply Chain Management felhasználói felületéről (UI) be lehet kapcsolni a tervezés optimalizálása funkcióját.</span><span class="sxs-lookup"><span data-stu-id="cf20f-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="cf20f-116">Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="cf20f-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="cf20f-117">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="cf20f-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="cf20f-118">Válassza a **karbantartás** lehetőséget, vagy görgessen a **környezeti bővítmények** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="cf20f-118">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="cf20f-119">Válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf20f-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="cf20f-120">Válassza a **Tervezés optimalizálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf20f-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="cf20f-121">Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.</span><span class="sxs-lookup"><span data-stu-id="cf20f-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="cf20f-122">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cf20f-122">Select **Install**.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="cf20f-123">A tervezésoptimalizálás integrációja</span><span class="sxs-lookup"><span data-stu-id="cf20f-123">Planning Optimization integration</span></span>

<span data-ttu-id="cf20f-124">Annak konfigurálásához, hogy a Tervezésoptimalizálás bővítményt használja-e a rendszer az alaptervezéshez, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezésoptimalizálás integrációja** \> **Integrációs paraméterek** pontot.</span><span class="sxs-lookup"><span data-stu-id="cf20f-124">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization integration** \> **Integration parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="cf20f-125">Kapcsolat állapota</span><span class="sxs-lookup"><span data-stu-id="cf20f-125">Connection status</span></span>

<span data-ttu-id="cf20f-126">A kapcsolat állapota jelzi a kapcsolat aktuális állapotát a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között.</span><span class="sxs-lookup"><span data-stu-id="cf20f-126">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="cf20f-127">A következő táblázat mutatja a lehetséges értékeket.</span><span class="sxs-lookup"><span data-stu-id="cf20f-127">The following table shows the possible values.</span></span>

| <span data-ttu-id="cf20f-128">Kapcsolat állapota</span><span class="sxs-lookup"><span data-stu-id="cf20f-128">Connection status</span></span> | <span data-ttu-id="cf20f-129">Leírás</span><span class="sxs-lookup"><span data-stu-id="cf20f-129">Description</span></span> | <span data-ttu-id="cf20f-130">Használható a Tervezésoptimalizálás?</span><span class="sxs-lookup"><span data-stu-id="cf20f-130">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="cf20f-131">Csatlakoztatva</span><span class="sxs-lookup"><span data-stu-id="cf20f-131">Connected</span></span> | <span data-ttu-id="cf20f-132">A rendszer kapcsolatot létesített a Tervezésoptimalizálás és a Supply Chain Management között.</span><span class="sxs-lookup"><span data-stu-id="cf20f-132">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="cf20f-133">Igen</span><span class="sxs-lookup"><span data-stu-id="cf20f-133">Yes</span></span> |
| <span data-ttu-id="cf20f-134">Kapcsolat engedélyezése</span><span class="sxs-lookup"><span data-stu-id="cf20f-134">Enabling connection</span></span> | <span data-ttu-id="cf20f-135">Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat bekapcsolási kérelme.</span><span class="sxs-lookup"><span data-stu-id="cf20f-135">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="cf20f-136">Nem</span><span class="sxs-lookup"><span data-stu-id="cf20f-136">No</span></span> |
| <span data-ttu-id="cf20f-137">Leválasztva</span><span class="sxs-lookup"><span data-stu-id="cf20f-137">Disconnected</span></span> | <span data-ttu-id="cf20f-138">Nincs kapcsolat a tervezés optimalizálása szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="cf20f-138">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="cf20f-139">A kapcsolat a következő témakörben leírtak szerint a LCS-ről kapcsolható be.</span><span class="sxs-lookup"><span data-stu-id="cf20f-139">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="cf20f-140">Nem</span><span class="sxs-lookup"><span data-stu-id="cf20f-140">No</span></span> |
| <span data-ttu-id="cf20f-141">Kapcsolat letiltása</span><span class="sxs-lookup"><span data-stu-id="cf20f-141">Disabling connection</span></span> | <span data-ttu-id="cf20f-142">Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat kikapcsolási kérelme.</span><span class="sxs-lookup"><span data-stu-id="cf20f-142">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="cf20f-143">Nem</span><span class="sxs-lookup"><span data-stu-id="cf20f-143">No</span></span> |
| <span data-ttu-id="cf20f-144">Állapot lekérése</span><span class="sxs-lookup"><span data-stu-id="cf20f-144">Getting status</span></span> | <span data-ttu-id="cf20f-145">A rendszer a tervezés optimalizálása szolgáltatásból származó állapotadatokra várakozik.</span><span class="sxs-lookup"><span data-stu-id="cf20f-145">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="cf20f-146">Nem</span><span class="sxs-lookup"><span data-stu-id="cf20f-146">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="cf20f-147">A Tervezésoptimalizálás beállítás használata</span><span class="sxs-lookup"><span data-stu-id="cf20f-147">The Use Planning Optimization option</span></span>

<span data-ttu-id="cf20f-148">A **Tervezés optimalizálása használata** beállítás határozza meg, hogy melyik tervezési motor használható az alaptervezéshez:</span><span class="sxs-lookup"><span data-stu-id="cf20f-148">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="cf20f-149">**Igen** – a tervezésoptimalizálás az alaptervezéshez használatos.</span><span class="sxs-lookup"><span data-stu-id="cf20f-149">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="cf20f-150">**Nem** – Az alaptervezéshez a Supply Chain Management beépített tervezési motorja használatos.</span><span class="sxs-lookup"><span data-stu-id="cf20f-150">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="cf20f-151">Ha meglévő tervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, elindulnak, miközben a **Tervezésoptimalizálás használata** beállítás értéke **Igen**, a feladatok sikertelenek lesznek.</span><span class="sxs-lookup"><span data-stu-id="cf20f-151">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="cf20f-152">Integráció a beállítással</span><span class="sxs-lookup"><span data-stu-id="cf20f-152">Integration with the setup</span></span>

<span data-ttu-id="cf20f-153">Ha a Tervezésoptimalizálás előzetes verziója be van kapcsolva, akkor az alaptervezést a rendszer a Tervezésoptimalizálás bővítménnyel végzi.</span><span class="sxs-lookup"><span data-stu-id="cf20f-153">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="cf20f-154">Ebben az esetben az Alaptervezés eredményeit és funkcióit érinti a program.</span><span class="sxs-lookup"><span data-stu-id="cf20f-154">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="cf20f-155">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="cf20f-155">Related resources</span></span>

[<span data-ttu-id="cf20f-156">Az előzetes verzió feltételei és kikötései</span><span class="sxs-lookup"><span data-stu-id="cf20f-156">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="cf20f-157">Tervezés optimalizálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="cf20f-157">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="cf20f-158">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="cf20f-158">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="cf20f-159">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="cf20f-159">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="cf20f-160">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="cf20f-160">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="cf20f-161">Tervezési feladat érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="cf20f-161">Cancel a planning job</span></span>](cancel-planning-job.md)
