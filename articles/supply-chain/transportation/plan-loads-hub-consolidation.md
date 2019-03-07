---
title: Rakományok tervezése központ-összevonás használatával
description: Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6743338819da3821cde18ec34a9c79290036ca23
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339947"
---
# <a name="plan-loads-using-hub-consolidation"></a><span data-ttu-id="d8f26-103">Rakományok tervezése központ-összevonás használatával</span><span class="sxs-lookup"><span data-stu-id="d8f26-103">Plan loads using hub consolidation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8f26-104">Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.</span><span class="sxs-lookup"><span data-stu-id="d8f26-104">This article describes the feature for consolidating shipments in a hub when you deliver goods from different warehouses to the same customer, or when you receive goods from multiple vendors in the same warehouse.</span></span>

<span data-ttu-id="d8f26-105">A szállítmányok központi összesítése eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén lehet hasznos.</span><span class="sxs-lookup"><span data-stu-id="d8f26-105">It can be useful to consolidate shipments in a hub when you deliver goods from different warehouses to the same customer, or when goods are delivered from multiple vendors to the same warehouse.</span></span>

## <a name="building-loads"></a><span data-ttu-id="d8f26-106">Rakományok összeállítása</span><span class="sxs-lookup"><span data-stu-id="d8f26-106">Building loads</span></span>
<span data-ttu-id="d8f26-107">Központ-összevonás előtt engedélyeznie kell a **Átmozgatás tervezése**beállítást a **Szállításkezelési paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d8f26-107">Before you can use hub consolidation, you must enable the **In transit planning** option on the **Transportation management parameters** page.</span></span> <span data-ttu-id="d8f26-108">Az összevonás számára létre kell hoznia központokat.</span><span class="sxs-lookup"><span data-stu-id="d8f26-108">You must also create the hubs where consolidation will occur.</span></span> <span data-ttu-id="d8f26-109">Az alábbi diagram központ-összevonást ábrázol.</span><span class="sxs-lookup"><span data-stu-id="d8f26-109">The following diagram shows an example of hub consolidation.</span></span> <span data-ttu-id="d8f26-110">Ebben az esetben különböző raktárakból származó vevői rendelések azonos vevőhöz kerülnek.</span><span class="sxs-lookup"><span data-stu-id="d8f26-110">In this case, sales orders from different warehouses are going to the same customer.</span></span> <span data-ttu-id="d8f26-111">Az alaprakományok vevői rendelések alapján jönnek létre a **Rakománytervező munkaterület** oldal használatával, a szokásos módon.</span><span class="sxs-lookup"><span data-stu-id="d8f26-111">The basic loads are created based on sales orders in the usual way, by using the **Load planning workbench** page.</span></span> <span data-ttu-id="d8f26-112">A két rakomány központi összevonásához a vevőhöz való kiszállítás előtt a **Rakománytervező munkaterület** oldalon a **Szállítás** mezőben válassza ki a **Központ-összevonás**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d8f26-112">To consolidate the two loads in a hub before they are delivered to the customer, on the **Load planning workbench** page, in the **Transportation** field, select **Hub consolidation**.</span></span> <span data-ttu-id="d8f26-113">Ha kijelöli minden rakomány helyes központját, a rakományok központja lesz a „lerakási” cél.</span><span class="sxs-lookup"><span data-stu-id="d8f26-113">When you select the correct hub for each load, the loads will have the hub as the “drop off” destination.</span></span> <span data-ttu-id="d8f26-114">Két „szállításigénylési sor” jelenik meg a **Készletek és igények** szakaszon a **Rakománytervező munkaterület** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d8f26-114">You will also have two “transportation request lines” in the **Supply and Demand** section on the **Load planning workbench** page.</span></span> <span data-ttu-id="d8f26-115">Majd hozzáadhatja ezeket a sorokat egy új rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="d8f26-115">You can then add these two lines to a new load.</span></span> <span data-ttu-id="d8f26-116">Az új rakomány értékesítésirendelés-sorokkal fog rendelkezni, a központ „felvételi” cím lesz, A vevő pedig „lerakási” cél.</span><span class="sxs-lookup"><span data-stu-id="d8f26-116">This new load will have both sales order lines, and will also have the hub as the “pick up” address and customer A as the “drop off” destination.</span></span> <span data-ttu-id="d8f26-117">A három rakomány díja és útvonala beállítható, mint bármely más rakományé.</span><span class="sxs-lookup"><span data-stu-id="d8f26-117">The three loads are then ready to be rated and routed like any other load.</span></span> <span data-ttu-id="d8f26-118">Bármelyik szállítmányozót választhatja rendszer által az egyes rakományokhoz javasoltak közül.</span><span class="sxs-lookup"><span data-stu-id="d8f26-118">You can select whatever shipping carrier the system suggests for each load.</span></span> <span data-ttu-id="d8f26-119">[![Központ-összevonás](./media/hubconsol.jpg)](./media/hubconsol.jpg) Többszörös átmozgatási rendelések esetén használhatja ugyanazt a módszert rakományok összesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d8f26-119">[![Hub consolidation](./media/hubconsol.jpg)](./media/hubconsol.jpg) You can also use the same method to consolidate loads for multiple transfer orders.</span></span> <span data-ttu-id="d8f26-120">Ebben az esetben, az előző ábrán A vevő egy raktár.</span><span class="sxs-lookup"><span data-stu-id="d8f26-120">In this case, customer A in the preceding diagram is a warehouse.</span></span> <span data-ttu-id="d8f26-121">Másik lehetőségként több beszerzési rendelés rakományát összesítheti eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.</span><span class="sxs-lookup"><span data-stu-id="d8f26-121">Alternatively, you can consolidate loads for multiple purchase orders, where the loads are delivered from different vendors to the same warehouse.</span></span> <span data-ttu-id="d8f26-122">Több, mint egy összevonás-központtal rendelkezhet és több, eltérő raktárakból származó rakományt összesíthet több központban.</span><span class="sxs-lookup"><span data-stu-id="d8f26-122">You can have more than one consolidation hub, and can consolidate in multiple hubs for more loads that come from different warehouses.</span></span> <span data-ttu-id="d8f26-123">Az alaprakományok összeállítása és az központi összevonás használata után az új rakományokat az összevont szállításigénylési sorok használatával állítja össze.</span><span class="sxs-lookup"><span data-stu-id="d8f26-123">After you build your basic loads and use the hub consolidation option, you build the new loads by using the consolidated transportation request lines.</span></span> <span data-ttu-id="d8f26-124">Majd állítsa be a rakomány díját és útvonalát.</span><span class="sxs-lookup"><span data-stu-id="d8f26-124">You then rate and route your loads.</span></span>



