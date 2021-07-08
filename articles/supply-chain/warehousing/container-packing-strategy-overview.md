---
title: Tárolócsomagolási stratégiák
description: Ez a témakör leírja a tárolócsomagolási stratégiák közötti különbségeket, és példákat mutat be.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292761"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="eae3d-103">Tárolócsomagolási stratégiák</span><span class="sxs-lookup"><span data-stu-id="eae3d-103">Container packing strategies</span></span>

<span data-ttu-id="eae3d-104">A *konténercsomagolási stratégia* olyan stratégia, amin a tárolók közötti cikkallokációk definiálhatók.</span><span class="sxs-lookup"><span data-stu-id="eae3d-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="eae3d-105">Ez a témakör bemutatja a *Csomagolás az összes nyitott tárolóba* és a *Csomagolás csak az aktuális tárolóba* stratégiák közötti különbségeket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="eae3d-106">**Csomagolás az összes nyitott tárolóba** – A rendszernek ellenőriznie kell az összes olyan nyitott tárolót, amely már létre lett hozva a tároló-létrehozási ciklus során, hogy a cikk biztosan elférjen valamelyikben.</span><span class="sxs-lookup"><span data-stu-id="eae3d-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="eae3d-107">A rendszer a csomagolás során mindegyik cikknél ellenőrzi, hogy befér-e valamelyik korábban létrehozott tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="eae3d-108">Ha a cikk nem fér bele egy meglévő tárolóba, a rendszer létrehoz egy új tárolót, és addig folytatja a csomagolást, amíg be nem fejeződik a teljes rendelés csomagolása.</span><span class="sxs-lookup"><span data-stu-id="eae3d-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="eae3d-109">Például *n* megrendelt cikk esetén tárolóra kell helyezni a tárolót.</span><span class="sxs-lookup"><span data-stu-id="eae3d-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="eae3d-110">Ebben a esetben a rendszer minden alkalommal, amikor olyan cikket dlgoz fel, amely nem fér bele egy meglévő tárolóba sem, összesen (\[(*n* – 1) × (*n* + 1)\] ÷ 2) ellenőrzi, hogy a cikk a meglévő tárolókban megfelelő-e.</span><span class="sxs-lookup"><span data-stu-id="eae3d-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="eae3d-111">**Csomagolás csak az aktuális tárolóba** – A rendszernek csak a legutóbb létrehozott tárolót kell ellenőriznie, hogy az elem biztosan beleférjen.</span><span class="sxs-lookup"><span data-stu-id="eae3d-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="eae3d-112">A rendszer a csomagolás során mindegyik cikknél ellenőrzi, hogy befér-e a legutóbb létrehozott tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="eae3d-113">Ha a cikk nem fér bele a meglévő tárolóba, a rendszer létrehoz egy új tárolót, és addig folytatja a csomagolást, amíg be nem fejeződik a teljes rendelés csomagolása.</span><span class="sxs-lookup"><span data-stu-id="eae3d-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="eae3d-114">Például *n* megrendelt cikk esetén tárolóra kell helyezni a tárolót.</span><span class="sxs-lookup"><span data-stu-id="eae3d-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="eae3d-115">Ebben a esetben a rendszer összesen (*n*–1) alkalommal ellenőrzi, hogy a cikk belefér-e a tárolókba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="eae3d-116">Példa a tárolócsomagolási stratégiák folyamatára</span><span class="sxs-lookup"><span data-stu-id="eae3d-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="eae3d-117">A következő elemeket állíthata be a tároláshoz.</span><span class="sxs-lookup"><span data-stu-id="eae3d-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="eae3d-118">Tétel</span><span class="sxs-lookup"><span data-stu-id="eae3d-118">Item</span></span> | <span data-ttu-id="eae3d-119">Fizikai dimenziók (szélesség × mélység × magasság)</span><span class="sxs-lookup"><span data-stu-id="eae3d-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="eae3d-120">Betűvastagság</span><span class="sxs-lookup"><span data-stu-id="eae3d-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="eae3d-121">HDMI-kábel 6 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-121">HDMI Cable 6'</span></span> | <span data-ttu-id="eae3d-122">1×1×1</span><span class="sxs-lookup"><span data-stu-id="eae3d-122">1 × 1 × 1</span></span> | <span data-ttu-id="eae3d-123">1</span><span class="sxs-lookup"><span data-stu-id="eae3d-123">1</span></span> |
| <span data-ttu-id="eae3d-124">HDMI-kábel 12 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-124">HDMI Cable 12'</span></span> | <span data-ttu-id="eae3d-125">2×1×1</span><span class="sxs-lookup"><span data-stu-id="eae3d-125">2 × 1 × 1</span></span> | <span data-ttu-id="eae3d-126">1</span><span class="sxs-lookup"><span data-stu-id="eae3d-126">1</span></span> |
| <span data-ttu-id="eae3d-127">HDMI-kábel 18 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-127">HDMI Cable 18'</span></span> | <span data-ttu-id="eae3d-128">3×1×1</span><span class="sxs-lookup"><span data-stu-id="eae3d-128">3 × 1 × 1</span></span> | <span data-ttu-id="eae3d-129">2</span><span class="sxs-lookup"><span data-stu-id="eae3d-129">2</span></span> |

<span data-ttu-id="eae3d-130">Beállíthatja következő dobozot is, amelyet a csomagoláshoz használnak.</span><span class="sxs-lookup"><span data-stu-id="eae3d-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="eae3d-131">Tároló</span><span class="sxs-lookup"><span data-stu-id="eae3d-131">Container</span></span> | <span data-ttu-id="eae3d-132">Fizikai dimenziók (hosszúság × szélesség × magasság)</span><span class="sxs-lookup"><span data-stu-id="eae3d-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="eae3d-133">Betűvastagság</span><span class="sxs-lookup"><span data-stu-id="eae3d-133">Weight</span></span> | <span data-ttu-id="eae3d-134">Térfogat</span><span class="sxs-lookup"><span data-stu-id="eae3d-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="eae3d-135">Közepes doboz</span><span class="sxs-lookup"><span data-stu-id="eae3d-135">Medium Box</span></span> | <span data-ttu-id="eae3d-136">6×3×2</span><span class="sxs-lookup"><span data-stu-id="eae3d-136">6 × 3 × 2</span></span> | <span data-ttu-id="eae3d-137">10</span><span class="sxs-lookup"><span data-stu-id="eae3d-137">10</span></span> | <span data-ttu-id="eae3d-138">100</span><span class="sxs-lookup"><span data-stu-id="eae3d-138">100</span></span> |

<span data-ttu-id="eae3d-139">Végül beállíthat egy rendelést, amely a következő termékeket és mennyiségeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="eae3d-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="eae3d-140">Értékesítésirendelés-sor</span><span class="sxs-lookup"><span data-stu-id="eae3d-140">Sales order line</span></span> | <span data-ttu-id="eae3d-141">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="eae3d-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="eae3d-142">HDMI-kábel 12 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-142">HDMI Cable 12'</span></span> | <span data-ttu-id="eae3d-143">9</span><span class="sxs-lookup"><span data-stu-id="eae3d-143">9</span></span> |
| <span data-ttu-id="eae3d-144">HDMI-kábel 18 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-144">HDMI Cable 18'</span></span> | <span data-ttu-id="eae3d-145">8</span><span class="sxs-lookup"><span data-stu-id="eae3d-145">8</span></span> |
| <span data-ttu-id="eae3d-146">HDMI-kábel 6 '</span><span class="sxs-lookup"><span data-stu-id="eae3d-146">HDMI Cable 6'</span></span> | <span data-ttu-id="eae3d-147">13</span><span class="sxs-lookup"><span data-stu-id="eae3d-147">13</span></span> |

<span data-ttu-id="eae3d-148">A következő táblázat összefoglalja, hogy hogyan működik a tárolás, amikor a *Csomagolás az összes nyitott tárolóba* vonatkozó stratégiában használja, és amikor a *Csomagolás csak az aktuális tárolóba* vonatkozó stratégiában használja.</span><span class="sxs-lookup"><span data-stu-id="eae3d-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="eae3d-149">Csomagolás minden nyitott tárolóba</span><span class="sxs-lookup"><span data-stu-id="eae3d-149">Pack into all open containers</span></span> | <span data-ttu-id="eae3d-150">Csomagolás az aktuális tárolóba</span><span class="sxs-lookup"><span data-stu-id="eae3d-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="eae3d-151">HDMI-kábel 12':</span><span class="sxs-lookup"><span data-stu-id="eae3d-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="eae3d-152">Új tárolótípus létrehozása, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="eae3d-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="eae3d-153">Tegyen 9 ea-t a CONT0001 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="eae3d-154">HDMI-kábel 12':</span><span class="sxs-lookup"><span data-stu-id="eae3d-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="eae3d-155">Új tárolótípus létrehozása, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="eae3d-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="eae3d-156">Tegyen 9 ea-t a CONT0001 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="eae3d-157">HDMI-kábel 18':</span><span class="sxs-lookup"><span data-stu-id="eae3d-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="eae3d-158">Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="eae3d-159">Új tárolótípus létrehozása, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="eae3d-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="eae3d-160">Tegyen 5 ea-t a CONT0002 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="eae3d-161">Új tárolótípus létrehozása, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="eae3d-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="eae3d-162">Tegyen 3 ea-t a CONT0003 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="eae3d-163">HDMI-kábel 18':</span><span class="sxs-lookup"><span data-stu-id="eae3d-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="eae3d-164">Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="eae3d-165">Új tárolótípus létrehozása, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="eae3d-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="eae3d-166">Tegyen 5 ea-t a CONT0002 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="eae3d-167">Új tárolótípus létrehozása, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="eae3d-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="eae3d-168">Tegyen 3 ea-t a CONT0003 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="eae3d-169">HDMI-kábel 6':</span><span class="sxs-lookup"><span data-stu-id="eae3d-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="eae3d-170">Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="eae3d-171">Tegyen 1 ea-t a CONT0001 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="eae3d-172">Ellenőrizze, hogy a cikk elfér-e a CONT0002 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="eae3d-173">Ellenőrizze, hogy a cikk elfér-e a CONT0003 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="eae3d-174">Tegyen 4 ea-t a CONT0003 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="eae3d-175">Új tárolótípus létrehozása, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="eae3d-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="eae3d-176">Tegyen 8 ea-t a CONT0004 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="eae3d-177">HDMI-kábel 6':</span><span class="sxs-lookup"><span data-stu-id="eae3d-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="eae3d-178">Ellenőrizze, hogy a cikk elfér-e a CONT0003 tárolóban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="eae3d-179">Tegyen 4 ea-t a CONT0003 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="eae3d-180">Új tárolótípus létrehozása, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="eae3d-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="eae3d-181">Tegyen 9 ea-t a CONT0004 tárolóba.</span><span class="sxs-lookup"><span data-stu-id="eae3d-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="eae3d-182">Példa erre: Egy rendelés csomagolása tárolónként</span><span class="sxs-lookup"><span data-stu-id="eae3d-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="eae3d-183">Ez a szakasz egy olyan helyzetet mutatja be, amelyben a rendszer úgy van beállítva, hogy több rendelést egyetlen szállítmányba vonja össze.</span><span class="sxs-lookup"><span data-stu-id="eae3d-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="eae3d-184">Ennek megfelelően a tárolás az értékesítési rendelésből történik, hogy a több terméket tartalmazó rendeléseket a saját tárolóiba csomagolják.</span><span class="sxs-lookup"><span data-stu-id="eae3d-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="eae3d-185">Ezzel a funkcióval olyan helyzetek kezelhetők, amikor minden egyes tárolóba csak egy értékesítési rendelést kell csomagolni, hogy az elosztási központ teljes tárolókat tudja kitárolni a kiskereskedelmi üzletek között.</span><span class="sxs-lookup"><span data-stu-id="eae3d-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="eae3d-186">A kiskereskedelmi helyzeteken kívül (rendelés kiskereskedelmi üzletenként és egy elosztási központhoz történő szállítás áttárolásra) ez a módszer a lean ellátási láncban (az egy időben történő termelési sorra vonatkozó értékesítési rendeléseknél) is használatos.</span><span class="sxs-lookup"><span data-stu-id="eae3d-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="eae3d-187">Ez az eset azt mutatja be, hogyan lehet csökkenteni a csomagolás során kiértékelt tárolók számát a *Csomagolás csak az aktuális tárolóba* vonatkozó stratégia használatával.</span><span class="sxs-lookup"><span data-stu-id="eae3d-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="eae3d-188">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="eae3d-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="eae3d-189">A Szállítmányok konszolidálása funkció bekapcsolása a rendszerben</span><span class="sxs-lookup"><span data-stu-id="eae3d-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="eae3d-190">Ez az eset a *Szállítmányok konszolidálása* funkciót használja.</span><span class="sxs-lookup"><span data-stu-id="eae3d-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="eae3d-191">Ha ez a funkció még nem érhető el a rendszerben, akkor be kell kapcsolnia azt a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével.</span><span class="sxs-lookup"><span data-stu-id="eae3d-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="eae3d-192">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="eae3d-192">Make demo data available</span></span>

<span data-ttu-id="eae3d-193">Ez a forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szabványos bemutató adataiban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="eae3d-194">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="eae3d-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="eae3d-195">Tárolótípusok vizsgálata vagy létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-195">Inspect or create container types</span></span>

<span data-ttu-id="eae3d-196">A tárolótípusok vizsgálatához vagy szükség esetén új tárolótípusok létrehozásához hajtsa végre ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-197">Ugorjon a **Warehouse Management** \> **Beállítás** \> **Tárolók** \> **Tárolótípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="eae3d-198">Győződjön meg róla, hogy a következő tárolótípusok mindegyike elérhető a bemutató adataiban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="eae3d-199">Tárolótípusok szerkesztése és létrehozása a szükségesek szerint.</span><span class="sxs-lookup"><span data-stu-id="eae3d-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="eae3d-200">1. tárolótípus:</span><span class="sxs-lookup"><span data-stu-id="eae3d-200">Container type 1:</span></span>

        - <span data-ttu-id="eae3d-201">**Tárolótípus kódja:** *Nagyméretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="eae3d-202">**Leírás:** *Nagy doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="eae3d-203">**Maximális nettó súly:** *100*</span><span class="sxs-lookup"><span data-stu-id="eae3d-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="eae3d-204">**Térfogat:** *400*</span><span class="sxs-lookup"><span data-stu-id="eae3d-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="eae3d-205">**Hossz:** *4*</span><span class="sxs-lookup"><span data-stu-id="eae3d-205">**Length:** *4*</span></span>
        - <span data-ttu-id="eae3d-206">**Szélesség:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-206">**Width:** *10*</span></span>
        - <span data-ttu-id="eae3d-207">**Magasság:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-207">**Height:** *10*</span></span>

    - <span data-ttu-id="eae3d-208">2. tárolótípus:</span><span class="sxs-lookup"><span data-stu-id="eae3d-208">Container type 2:</span></span>

        - <span data-ttu-id="eae3d-209">**Tárolótípus kódja:** *Közepes méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="eae3d-210">**Leírás:** *Közepes doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="eae3d-211">**Maximális nettó súly:** *50*</span><span class="sxs-lookup"><span data-stu-id="eae3d-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="eae3d-212">**Térfogat:** *200*</span><span class="sxs-lookup"><span data-stu-id="eae3d-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="eae3d-213">**Hossz:** *2*</span><span class="sxs-lookup"><span data-stu-id="eae3d-213">**Length:** *2*</span></span>
        - <span data-ttu-id="eae3d-214">**Szélesség:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-214">**Width:** *10*</span></span>
        - <span data-ttu-id="eae3d-215">**Magasság:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-215">**Height:** *10*</span></span>

    - <span data-ttu-id="eae3d-216">3. tárolótípus:</span><span class="sxs-lookup"><span data-stu-id="eae3d-216">Container type 3:</span></span>

        - <span data-ttu-id="eae3d-217">**Tárolótípus kódja:** *Kisméretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="eae3d-218">**Leírás:** *Kis doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="eae3d-219">**Maximális nettó súly:** *20*</span><span class="sxs-lookup"><span data-stu-id="eae3d-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="eae3d-220">**Térfogat:** *100*</span><span class="sxs-lookup"><span data-stu-id="eae3d-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="eae3d-221">**Hossz:** *1*</span><span class="sxs-lookup"><span data-stu-id="eae3d-221">**Length:** *1*</span></span>
        - <span data-ttu-id="eae3d-222">**Szélesség:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-222">**Width:** *10*</span></span>
        - <span data-ttu-id="eae3d-223">**Magasság:** *10*</span><span class="sxs-lookup"><span data-stu-id="eae3d-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="eae3d-224">Tárolócsoportok vizsgálata vagy létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-224">Inspect or create container groups</span></span>

<span data-ttu-id="eae3d-225">A tárolócsoportok vizsgálatához vagy szükség esetén új tárolócsoportok létrehozásához hajtsa végre ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-226">Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolócsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="eae3d-227">Győződjön meg róla, hogy a következő tárolócsoportok mindegyike elérhető a bemutató adataiban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="eae3d-228">Ha nem érhető el, a létrehozáshoz válassza az **Új** gombot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="eae3d-229">**Tárolócsoport azonosítója:** *Dobozok*</span><span class="sxs-lookup"><span data-stu-id="eae3d-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="eae3d-230">**Leírás:** *Dobozméretek*</span><span class="sxs-lookup"><span data-stu-id="eae3d-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="eae3d-231">A *Dobozok* tárolócsoport **Részletek** gyorscsoportján ellenőrizze, hogy léteznek-e a következő sorok.</span><span class="sxs-lookup"><span data-stu-id="eae3d-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="eae3d-232">Ha nem, az **Új** gombbal hozzáadhatja azokat.</span><span class="sxs-lookup"><span data-stu-id="eae3d-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="eae3d-233">1. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-233">Line 1:</span></span>

        - <span data-ttu-id="eae3d-234">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="eae3d-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="eae3d-235">**Tároló típusa:** *Nagyméretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="eae3d-236">**Tároló százalékos kihasználtsága:** *100*</span><span class="sxs-lookup"><span data-stu-id="eae3d-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="eae3d-237">2. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-237">Line 2:</span></span>

        - <span data-ttu-id="eae3d-238">**Sorszám:** *2*</span><span class="sxs-lookup"><span data-stu-id="eae3d-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="eae3d-239">**Tárolótípus:** *Közepes méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="eae3d-240">**Tároló százalékos kihasználtsága:** *100*</span><span class="sxs-lookup"><span data-stu-id="eae3d-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="eae3d-241">3. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-241">Line 3:</span></span>

        - <span data-ttu-id="eae3d-242">**Sorszám:** *3*</span><span class="sxs-lookup"><span data-stu-id="eae3d-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="eae3d-243">**Tárolótípus:** *Kisméretű doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="eae3d-244">**Tároló százalékos kihasználtsága:** *100*</span><span class="sxs-lookup"><span data-stu-id="eae3d-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="eae3d-245">Új tárolóépítési sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-245">Create a new container build template</span></span>

<span data-ttu-id="eae3d-246">Új tárolóépítési sablon létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-247">Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolóépítési sablon** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="eae3d-248">Válassza az **Új** lehetőséget, ha olyan tárolóépítési sablont hoz létre, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="eae3d-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="eae3d-249">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="eae3d-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="eae3d-250">**Tárolósablon azonosítója:** *Doboz*</span><span class="sxs-lookup"><span data-stu-id="eae3d-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="eae3d-251">**Tárolócsoport azonosítója:** *Dobozok*</span><span class="sxs-lookup"><span data-stu-id="eae3d-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="eae3d-252">**Alap lekérdezéstípusok:** *Értékesítési felosztási sor*</span><span class="sxs-lookup"><span data-stu-id="eae3d-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="eae3d-253">**Hullámlépés kódja:** *234*</span><span class="sxs-lookup"><span data-stu-id="eae3d-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="eae3d-254">**Kiválsztás engedélyezése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="eae3d-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="eae3d-255">**Tároló csomagolási stratégiája:** *Csomagolás csak az aktuális tárolóba*</span><span class="sxs-lookup"><span data-stu-id="eae3d-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="eae3d-256">**Csomagolás az irányelvegység szerint:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="eae3d-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="eae3d-257">Amíg az új sablon sora még ki van választva, válassza ki a **Lekérdezés szerkesztése** lehetőséget a Műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="eae3d-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="eae3d-258">Megjelenik egy szabványos lekérdezésszerkesztő párbeszédpanelje.</span><span class="sxs-lookup"><span data-stu-id="eae3d-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="eae3d-259">A **Rendezés** lapon válassza a **Hozzáadást** egy sort hozzáadásához a rácshoz a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="eae3d-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="eae3d-260">**Tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="eae3d-261">**Származtatott tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="eae3d-262">**Mező:** *Rendelés száma*</span><span class="sxs-lookup"><span data-stu-id="eae3d-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="eae3d-263">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="eae3d-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eae3d-264">A többi nyitott tároló túlárazásának elkerülése érdekében, illetve a folyamat felgyorsítása érdekében egyszerre egy tárolót ellenőriz, a rendelésszámok szerint történő rendezésen kívül a *Csomagolás csak az aktuális tárolóba* stratégia használható.</span><span class="sxs-lookup"><span data-stu-id="eae3d-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="eae3d-265">Ez a kombináció munkaszünetként fog működni egy munkasablonon.</span><span class="sxs-lookup"><span data-stu-id="eae3d-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="eae3d-266">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="eae3d-267">Amíg az új sablon sora még ki van választva, válassza ki a **Tárolóvegyesítési megszorítások** lehetőséget a Műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="eae3d-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="eae3d-268">Ezzel olyan megszorítást fog hozzáadni, amely egyetlen rendelés cikkét egyetlen tárolóba helyezi.</span><span class="sxs-lookup"><span data-stu-id="eae3d-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="eae3d-269">A más rendelésből származó cikkek külön tárolóba lesznek ásva.</span><span class="sxs-lookup"><span data-stu-id="eae3d-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="eae3d-270">Válassza az **Új** lehetőséget, ha olyan vegyítési megszorításokat hoz létre, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="eae3d-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="eae3d-271">**Tábla:** *Értékesítési rendelések*</span><span class="sxs-lookup"><span data-stu-id="eae3d-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="eae3d-272">**Mező kiválasztása:** *SalesId* (A mező *Értékesítési rendelésként* jelenik meg a rácsban.)</span><span class="sxs-lookup"><span data-stu-id="eae3d-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="eae3d-273">A megszorítás hozzáadásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="eae3d-274">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="eae3d-275">Hullámsablon beálllítása a tárolóra bontáshoz</span><span class="sxs-lookup"><span data-stu-id="eae3d-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="eae3d-276">Hullámsablon beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-277">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="eae3d-278">A listatáblában állítsa a **Hullámsablon típusa** mezőt a *Szállítás* értékre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="eae3d-279">Válassz a **63 tárolóra bontás** sablont a listában.</span><span class="sxs-lookup"><span data-stu-id="eae3d-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="eae3d-280">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="eae3d-281">A **Módok** gyorslapon, a **Kiválasztott módok** oszlopban keresse meg a következő sort:</span><span class="sxs-lookup"><span data-stu-id="eae3d-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="eae3d-282">**Metódus neve:** *tárolóra bontás*</span><span class="sxs-lookup"><span data-stu-id="eae3d-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="eae3d-283">**Név:** *Tárolóra bontás*</span><span class="sxs-lookup"><span data-stu-id="eae3d-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="eae3d-284">Ehhez a sorhoz állítsa a **Hullámlépés kód** mezőt a *234* lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="eae3d-285">Munkasablon beállítása</span><span class="sxs-lookup"><span data-stu-id="eae3d-285">Set up a work template</span></span>

<span data-ttu-id="eae3d-286">Munkasablon beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-287">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="eae3d-288">A **Munkarendelés típusa** mező beállítása a *Beszerzési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="eae3d-289">Az **Áttekintés** rácsban keresse meg és válassza ki azt munkasablont, amelyet konténerenként egyes megrendelések csomagolásához kell használni.</span><span class="sxs-lookup"><span data-stu-id="eae3d-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="eae3d-290">Ehhez a helyzethez válassza az **63 Kitárolás tárolóhoz** sablont.</span><span class="sxs-lookup"><span data-stu-id="eae3d-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="eae3d-291">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="eae3d-292">Megjelenik egy szabványos lekérdezésszerkesztő párbeszédpanelje.</span><span class="sxs-lookup"><span data-stu-id="eae3d-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="eae3d-293">A **Rendezés** lapon adja meg a következő sorok beállításait:</span><span class="sxs-lookup"><span data-stu-id="eae3d-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="eae3d-294">1. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-294">Line 1:</span></span>

        - <span data-ttu-id="eae3d-295">**Tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-296">**Származtatott tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-297">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="eae3d-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="eae3d-298">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="eae3d-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="eae3d-299">2. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-299">Line 2:</span></span>

        - <span data-ttu-id="eae3d-300">**Tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-301">**Származtatott tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-302">**Mező:** *Rendelés száma*</span><span class="sxs-lookup"><span data-stu-id="eae3d-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="eae3d-303">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="eae3d-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="eae3d-304">3. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-304">Line 3:</span></span>

        - <span data-ttu-id="eae3d-305">**Tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-306">**Származtatott tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="eae3d-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="eae3d-307">**Mező:** *Tároló azonosítója*</span><span class="sxs-lookup"><span data-stu-id="eae3d-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="eae3d-308">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="eae3d-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="eae3d-309">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="eae3d-310">A következő üzenet jelenik meg: „A csoportosítás alaphelyzetbe kerül, folytatja?”</span><span class="sxs-lookup"><span data-stu-id="eae3d-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="eae3d-311">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="eae3d-312">Amíg a **63 Kitárolás tárolóhoz** sablon ki van választva, jelölje ki a **Munkafejléc-szüneteket** a Munkaablakban.</span><span class="sxs-lookup"><span data-stu-id="eae3d-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="eae3d-313">Ezzel a beállítások alkalmazásával megszakítja a munkát, hogy a rendelés minden tárolója egy munkarendeléshez kapcsolódjön.</span><span class="sxs-lookup"><span data-stu-id="eae3d-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="eae3d-314">Jelölje be a **Csoportosítás a mező szerint** jelölőnégyzetet a **Munkafejléc-törések** lap (**Szállítmányazonosító**, **Rendelésszám** és **Tárolóazonosító**) minden sorában.</span><span class="sxs-lookup"><span data-stu-id="eae3d-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="eae3d-315">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="eae3d-316">Szállítmánykonszolidációs irányelvek beállítása</span><span class="sxs-lookup"><span data-stu-id="eae3d-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="eae3d-317">A szállítási konszolidáció irányelvének beállításához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-318">Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="eae3d-319">A listatáblában állítsa át az **Irányelv típusa** mezőt *Értékesítési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="eae3d-320">Válassza ki az **Alapértelmezett** irányelveket a listából.</span><span class="sxs-lookup"><span data-stu-id="eae3d-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="eae3d-321">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="eae3d-322">A **Konszolidációs mezők** gyorslapon a **Kiválasztott mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Rendelési szám*.</span><span class="sxs-lookup"><span data-stu-id="eae3d-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="eae3d-323">Válassza az **Eltávolatás** gombot ![Balra nyíl](media/backward-button.png) a mező **Hátralévő mezők** listára történő átmozgatásához.</span><span class="sxs-lookup"><span data-stu-id="eae3d-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="eae3d-324">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="eae3d-325">Állítsa be a termék fizikai méreteit</span><span class="sxs-lookup"><span data-stu-id="eae3d-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="eae3d-326">Az ilyen helyzetekben használt termékek fizikai dimenzióinak beállítását a következő lépések szerint hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-327">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="eae3d-328">Annak a terméknek a kiválasztása, ahol a **Cikkszám** mező beállítása *A0001*.</span><span class="sxs-lookup"><span data-stu-id="eae3d-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="eae3d-329">A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="eae3d-330">A **Fizikai dimenziók** lapon a következő sort kell látnia a rácsban:</span><span class="sxs-lookup"><span data-stu-id="eae3d-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="eae3d-331">**Egység:** *db*</span><span class="sxs-lookup"><span data-stu-id="eae3d-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="eae3d-332">**Bruttó tömeg:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="eae3d-333">**Szélesség:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="eae3d-334">**Mélység:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="eae3d-335">**Magasság:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="eae3d-336">**Térfogat:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="eae3d-337">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-337">Close the page.</span></span>
1. <span data-ttu-id="eae3d-338">Annak a terméknek a kiválasztása, ahol a **Cikkszám** mező beállítása *A0002*.</span><span class="sxs-lookup"><span data-stu-id="eae3d-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="eae3d-339">A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="eae3d-340">A **Fizikai dimenziók** lapon a következő sort kell látnia a rácsban:</span><span class="sxs-lookup"><span data-stu-id="eae3d-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="eae3d-341">**Egység:** *db*</span><span class="sxs-lookup"><span data-stu-id="eae3d-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="eae3d-342">**Bruttó tömeg:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="eae3d-343">**Szélesség:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="eae3d-344">**Mélység:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="eae3d-345">**Magasság:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="eae3d-346">**Térfogat:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="eae3d-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="eae3d-347">1. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-347">Create sales order 1</span></span>

<span data-ttu-id="eae3d-348">Értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-349">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="eae3d-350">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="eae3d-351">Megjelenik egy párbeszédpanel az új értékesítési rendelések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="eae3d-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="eae3d-352">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="eae3d-352">Set the following values:</span></span>

    - <span data-ttu-id="eae3d-353">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="eae3d-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="eae3d-354">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="eae3d-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="eae3d-355">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="eae3d-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="eae3d-356">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="eae3d-356">The new sales order is opened.</span></span> <span data-ttu-id="eae3d-357">Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő értékesítési sorokat:</span><span class="sxs-lookup"><span data-stu-id="eae3d-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="eae3d-358">1. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-358">Line 1:</span></span>

        - <span data-ttu-id="eae3d-359">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="eae3d-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="eae3d-360">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="eae3d-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="eae3d-361">2. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-361">Line 2:</span></span>

        - <span data-ttu-id="eae3d-362">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="eae3d-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="eae3d-363">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="eae3d-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="eae3d-364">Válassza ki az első sort, majd válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="eae3d-365">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="eae3d-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="eae3d-366">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="eae3d-366">Then close the page.</span></span>
1. <span data-ttu-id="eae3d-367">Ismételje meg az előző két lépést a második sorra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="eae3d-368">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="eae3d-369">2. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-369">Create sales order 2</span></span>

<span data-ttu-id="eae3d-370">íegy második értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-371">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="eae3d-372">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="eae3d-373">Megjelenik egy párbeszédpanel az új értékesítési rendelések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="eae3d-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="eae3d-374">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="eae3d-374">Set the following values:</span></span>

    - <span data-ttu-id="eae3d-375">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="eae3d-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="eae3d-376">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="eae3d-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="eae3d-377">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="eae3d-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="eae3d-378">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="eae3d-378">The new sales order is opened.</span></span> <span data-ttu-id="eae3d-379">Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő értékesítési sorokat:</span><span class="sxs-lookup"><span data-stu-id="eae3d-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="eae3d-380">1. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-380">Line 1:</span></span>

        - <span data-ttu-id="eae3d-381">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="eae3d-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="eae3d-382">**Mennyiség:** *4*</span><span class="sxs-lookup"><span data-stu-id="eae3d-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="eae3d-383">2. sor:</span><span class="sxs-lookup"><span data-stu-id="eae3d-383">Line 2:</span></span>

        - <span data-ttu-id="eae3d-384">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="eae3d-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="eae3d-385">**Mennyiség:** *4*</span><span class="sxs-lookup"><span data-stu-id="eae3d-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="eae3d-386">Válassza ki az első sort, majd válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="eae3d-387">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="eae3d-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="eae3d-388">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="eae3d-388">Then close the page.</span></span>
1. <span data-ttu-id="eae3d-389">Ismételje meg az előző két lépést a második sorra.</span><span class="sxs-lookup"><span data-stu-id="eae3d-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="eae3d-390">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="eae3d-391">Terhelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="eae3d-391">Create the load</span></span>

<span data-ttu-id="eae3d-392">A következő lépések végrehajtásával terhelést hozhat létre az egyes rendeléskészletekhez, amelyeket ehhez az esethez készített, majd kiadhatja azt a raktárnak.</span><span class="sxs-lookup"><span data-stu-id="eae3d-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="eae3d-393">Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.</span><span class="sxs-lookup"><span data-stu-id="eae3d-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="eae3d-394">Az **Értékesítési sorok** lapon megkeresheti és kiválaszthatja az adott esethez létrehozott rendeléskészletek értékesítési rendelési sorait.</span><span class="sxs-lookup"><span data-stu-id="eae3d-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="eae3d-395">A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet.</span><span class="sxs-lookup"><span data-stu-id="eae3d-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="eae3d-396">A kiválasztott rendeléssorok új rakományhoz adódnak hozzá.</span><span class="sxs-lookup"><span data-stu-id="eae3d-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="eae3d-397">A **Rakománysablon hozzárendelése** párbeszédablakban a **Rakománysablon azonosítója** mezőben válassza ki a rakománysablont, pl. a *40' Tároló* elemet.</span><span class="sxs-lookup"><span data-stu-id="eae3d-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="eae3d-398">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="eae3d-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="eae3d-399">A **Rakomány** szakaszban keresse meg és válassza ki az imént létrehozott rakományt.</span><span class="sxs-lookup"><span data-stu-id="eae3d-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="eae3d-400">Válassza a **Kiadás \> Raktárba való kiadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eae3d-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="eae3d-401">A kiválasztott rakomány raktárba történő kiadásához nyomja meg a **Kiadás a raktárba** párbeszédablakon az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="eae3d-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="eae3d-402">A szállítmányok és a tárolók ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="eae3d-402">Verify the shipments and containers</span></span>

<span data-ttu-id="eae3d-403">Az alábbi eljárásokkal ellenőrizhetők a létrehozott szállítmányok.</span><span class="sxs-lookup"><span data-stu-id="eae3d-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="eae3d-404">Használatával áttekinthető az esethez létrehozott rendelés, így biztosan meg tudja szerezni a várt eredményeket.</span><span class="sxs-lookup"><span data-stu-id="eae3d-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="eae3d-405">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="eae3d-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="eae3d-406">Az előbb kiadott rakományhoz létrehozott szállítmány megkeresése és kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="eae3d-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="eae3d-407">A Művelet ablakban a **Szállítás** lapon, válassza a **Tárolók megtekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="eae3d-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="eae3d-408">Győződjön meg arról, hogy az értékesítési rendelések cikkeit két különböző tárolóba rakták.</span><span class="sxs-lookup"><span data-stu-id="eae3d-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eae3d-409">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="eae3d-409">Additional resources</span></span>

- [<span data-ttu-id="eae3d-410">Tárolóra bontás</span><span class="sxs-lookup"><span data-stu-id="eae3d-410">Containerization</span></span>](wave-containerization.md)
