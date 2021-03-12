---
title: Tervezett rendelések jóváhagyása
description: Ez a témakör a Tervezés optimalizálása során támogatott tervezett rendelések jóváhagyását írja le.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c29ede7ad8916a97b4a04b68f41961f79810e0c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983569"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="d6807-103">Tervezett rendelések jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="d6807-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6807-104">Ez a témakör a tervezett rendelések állapotának a Tervezés optimalizálásában történő frissítésével kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="d6807-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="d6807-105">Ne feledje, hogy a tervezett rendelések jóváhagyása nem kötelező lépés, amellyel megerősített rendelést hozhat létre egy tervezett rendelésből.</span><span class="sxs-lookup"><span data-stu-id="d6807-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="d6807-106">Ajánlott jóváhagyni a módosított tervezett rendeléseket, különben a program figyelmen kívül hagyja a módosításokat, és a következő tervezés futtatásakor felülírja őket.</span><span class="sxs-lookup"><span data-stu-id="d6807-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Tervezett rendelés folyamata](media/approved-planned-orders-1.png)

<span data-ttu-id="d6807-108">Az **Állapot** mező a következő értékek használatával segít a folyamat követésében:</span><span class="sxs-lookup"><span data-stu-id="d6807-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="d6807-109">**Feldolgozatlan** Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota *Feldolgozatlan*.</span><span class="sxs-lookup"><span data-stu-id="d6807-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="d6807-110">Az ilyen állapotú tervezett rendeléseket a program a következő tervezés futtatásakor törli.</span><span class="sxs-lookup"><span data-stu-id="d6807-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="d6807-111">**Befejezve:** Ha úgy dönt, hogy nem erősít meg egy tervezett rendelést, akkor az állapot *Befejezett* értékre módosításával jelezheti, hogy befejezte a tervezett rendelés kiértékelését.</span><span class="sxs-lookup"><span data-stu-id="d6807-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="d6807-112">Ne feledje, hogy a rendszer a *Feldolgozatlan* és a *Befejezett* állapotot ugyanúgy kezeli.</span><span class="sxs-lookup"><span data-stu-id="d6807-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="d6807-113">**Jóváhagyva:** Ha meg akarja tartabi a módosításokat, vagy tervezett rendelést szeretne megerősíteni, akkor módosítsa az állapotot *Jóváhagyott* értékre.</span><span class="sxs-lookup"><span data-stu-id="d6807-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="d6807-114">Az Alaptervezés megerősített és várt ellátásnak veszi a *Jóváhagyott* állapotú tervezett rendeléseket, így azokat nem módosítja vagy nem törli a program későbbi alaptervezés futtatása során.</span><span class="sxs-lookup"><span data-stu-id="d6807-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="d6807-115">Ennek elérése érdekében a tervezési logika átmásolja a *Jóváhagyott* tervezett rendeléseket a régi terv verzióból az új terv verzióba az alaptervezés során.</span><span class="sxs-lookup"><span data-stu-id="d6807-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="d6807-116">Ne felejtse el, hogy a *Jóváhagyott* tervezett rendelések csak az adott alaptervben számítanak ellátásnak.</span><span class="sxs-lookup"><span data-stu-id="d6807-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="d6807-117">A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban.</span><span class="sxs-lookup"><span data-stu-id="d6807-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>
