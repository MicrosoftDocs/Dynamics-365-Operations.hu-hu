---
title: Tervezett rendelések megtekintése, kezelése és jóváhagyása
description: Ez a témakör a tervezett rendelések a Tervezésoptimalizálásban történő megtekintésével, kezelésével és jóváhagyásával kapcsolatban tartalmaz tájékoztatást.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935657"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="0150d-103">Tervezett rendelések megtekintése, kezelése és jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="0150d-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0150d-104">Ez a témakör a tervezett rendelések a Tervezésoptimalizálásban történő megtekintésével, kezelésével és jóváhagyásával kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="0150d-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="0150d-105">Tervezett rendelések megtekintése és kezelése</span><span class="sxs-lookup"><span data-stu-id="0150d-105">View and manage planned orders</span></span>

<span data-ttu-id="0150d-106">A tervezett rendelések bármely tervezett rendelési listaoldalon megtekinthetők és kezelhetők.</span><span class="sxs-lookup"><span data-stu-id="0150d-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="0150d-107">A munkához használni kívánt tervezett rendelések típusától függően lépjen a következő helyek egyikére:</span><span class="sxs-lookup"><span data-stu-id="0150d-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="0150d-108">Alaptervezés \> Munkaterületek \> Alaptervezés</span><span class="sxs-lookup"><span data-stu-id="0150d-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="0150d-109">Alaptervezés \> Alaptervezés \> Tervezett rendelések</span><span class="sxs-lookup"><span data-stu-id="0150d-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="0150d-110">Gyártásvezérlés \> Termelési rendelések \> Tervezett termelési rendelések</span><span class="sxs-lookup"><span data-stu-id="0150d-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="0150d-111">Beszerzés és forrás \> Beszerzési rendelés \> Tervezett beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="0150d-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="0150d-112">Készletnyilvántartás \> Bejövő rendelések \> Tervezett átmozgatások</span><span class="sxs-lookup"><span data-stu-id="0150d-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="0150d-113">Készletnyilvántartás \> Kimenő rendelések \> Tervezett átmozgatások</span><span class="sxs-lookup"><span data-stu-id="0150d-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="0150d-114">A tervezett rendelések állapotának megtekintése és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="0150d-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="0150d-115">Az egyes tervezett rendelések **Állapot** mezőjével nyomon követheti az előrehaladást, illetve módosíthatja a tervezett rendelések feldolgozásának módját.</span><span class="sxs-lookup"><span data-stu-id="0150d-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="0150d-116">A következő **Állapot** értékek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="0150d-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="0150d-117">**Feldolgozatlan** – Amikor az alaptervezés tervezett rendeléseket készít, akkor ezt az állapotot kapják.</span><span class="sxs-lookup"><span data-stu-id="0150d-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="0150d-118">Az ilyen állapotú tervezett rendeléseket a program a következő tervezés futtatásakor törli.</span><span class="sxs-lookup"><span data-stu-id="0150d-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="0150d-119">**Befejeződött** – Ez az állapot azt jelzi, hogy a tervezett rendelést befejezték.</span><span class="sxs-lookup"><span data-stu-id="0150d-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="0150d-120">Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor manuálisan is módosíthatja az állapotát *Befejeződött* értékre.</span><span class="sxs-lookup"><span data-stu-id="0150d-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="0150d-121">Ne feledje, hogy a rendszer a *Feldolgozatlan* és a *Befejezett* állapotot ugyanúgy kezeli.</span><span class="sxs-lookup"><span data-stu-id="0150d-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="0150d-122">**Jóváhagyva** – Ez az állapot azt jelzi, hogy a tervezett rendelést jóváhagyták megerősítésre.</span><span class="sxs-lookup"><span data-stu-id="0150d-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="0150d-123">Ha meg szeretné határozni a tervezett rendelést, akkor a *Jóváhagyott* állapotra módosítható.</span><span class="sxs-lookup"><span data-stu-id="0150d-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="0150d-124">Ha meg szeretné tartani a tervezett rendelésen történt módosításokat, vagy ha egy tervezett rendelés megerősítését tervezi, módosítsa a tervezett rendelés állapotát *Jóváhagyott* értékre.</span><span class="sxs-lookup"><span data-stu-id="0150d-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="0150d-125">Az alaptervezés rögzítettnek és várható készletnek minősíti a *Jóváhagyott* állapotú tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="0150d-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="0150d-126">Ezért ezek nem módosulnak és nem törlődnek a későbbi alaptervezési futások során.</span><span class="sxs-lookup"><span data-stu-id="0150d-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="0150d-127">A viselkedés elérése érdekében a tervezési logika átmásolja a *Jóváhagyott* állapotú tervezett rendeléseket a régi terv verzióból az új terv verzióba az alaptervezés során.</span><span class="sxs-lookup"><span data-stu-id="0150d-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="0150d-128">Ne felejtse el, hogy a *Jóváhagyott* állapotú tervezett rendelések csak az adott alaptervben számítanak ellátásnak.</span><span class="sxs-lookup"><span data-stu-id="0150d-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="0150d-129">Ha egyetlen tervezett rendelés állapotát kell módosítani, [nyissa meg a tervezett rendelések listaoldalát](#view-planned-orders), nyissa meg a rendelést, majd hajtsa végre a következő lépések valamelyikét:</span><span class="sxs-lookup"><span data-stu-id="0150d-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="0150d-130">Az **Általános** gyorslapon módosítsa az **Állapot** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="0150d-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="0150d-131">A Művelet ablaktábla **Tervezett rendelés** lapjának **Feldolgozás** csoportjában válassza az **Állapot módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="0150d-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="0150d-132">A rendelés jóváhagyottként való megjelöléséhez válassza a **Jóváhagyás** lehetőséget a Műveletpanelen.</span><span class="sxs-lookup"><span data-stu-id="0150d-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="0150d-133">Ha egyszerre több tervezett rendelés állapotát is módosítani szeretné, [nyissa meg a tervezett rendelések listaoldalát](#view-planned-orders), jelölje be mindegyik módosítani kívánt rendelés jelölőnégyzetét, majd hajtsa végre a következő lépések valamelyikét:</span><span class="sxs-lookup"><span data-stu-id="0150d-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="0150d-134">A Művelet ablaktábla **Tervezett rendelés** lapjának **Feldolgozás** csoportjában válassza az **Állapot módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="0150d-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="0150d-135">A rendelések jóváhagyottként való megjelöléséhez válassza a **Jóváhagyás** lehetőséget a Műveletpanelen.</span><span class="sxs-lookup"><span data-stu-id="0150d-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="0150d-136">Tervezett rendelések jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="0150d-136">Approve planned orders</span></span>

<span data-ttu-id="0150d-137">A tervezett rendelések jóváhagyása nem kötelező lépés a megerősített rendelés egy tervezett rendelésből való létrehozásának folyamatában.</span><span class="sxs-lookup"><span data-stu-id="0150d-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="0150d-138">A következő ábra bemutatja, hogy hogyan lehet a jóváhagyási munkafolyamat megvalósításához használni az egyes tervezett rendelésekhez hozzárendelt **Állapot** értéket.</span><span class="sxs-lookup"><span data-stu-id="0150d-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="0150d-139">A jóváhagyási folyamat megvalósításához manuálisan módosítsa az egyes tervezett rendelések **Állapot** értékét az előző szakaszban leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="0150d-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Tervezett rendelés folyamata](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="0150d-141">Javasoljuk, hogy hagyja jóvá a módosított tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="0150d-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="0150d-142">Ellenkező esetben a rendszer figyelmen kívül hagyja a módosításokat, és felülírja őket a következő tervezési futtatás során.</span><span class="sxs-lookup"><span data-stu-id="0150d-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0150d-143">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0150d-143">Additional resources</span></span>

- [<span data-ttu-id="0150d-144">Biztosra tervezett rendelések</span><span class="sxs-lookup"><span data-stu-id="0150d-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
