---
title: Műveletek szabálytalanságokhoz kapcsolódóan
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó műveleteket.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956690"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="b96df-103">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="b96df-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b96df-104">Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó műveleteket.</span><span class="sxs-lookup"><span data-stu-id="b96df-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="b96df-105">A **Műveletek** lapot használhatja a jóváhagyott szabálytalanságokon elvégezhető műveletek osztályzásához.</span><span class="sxs-lookup"><span data-stu-id="b96df-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="b96df-106">Amikor a szabálytalansághoz egy kapcsolódó műveletet rendel, részleteket adhat meg a kapcsolódó anyagról, például a munkaidőről és költségekről, amelyek a művelet végrehajtásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="b96df-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="b96df-107">A rendszer ezen információ alapján számítja ki a művelet becsült költségét.</span><span class="sxs-lookup"><span data-stu-id="b96df-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="b96df-108">A részletes adatok és a becsült költségek csak tájékoztató jellegűek.</span><span class="sxs-lookup"><span data-stu-id="b96df-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="b96df-109">A minőséggel kapcsolatos műveletek nem olyan műveletek, mint a termelési útvonalban meghatározható műveletek.</span><span class="sxs-lookup"><span data-stu-id="b96df-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="b96df-110">Bár a szabálytalansághoz kapcsolódó műveletben nyomon követhetők a költségek, az idő és a cikkek, a beírható adatok csak tájékoztató jellegűek.</span><span class="sxs-lookup"><span data-stu-id="b96df-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="b96df-111">Nem integrálódik automatikusan a főkönyvvel, a készlet főkönyvével vagy a **Munkaidő és jelenlét** modullal.</span><span class="sxs-lookup"><span data-stu-id="b96df-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="b96df-112">Példák a műveletekre</span><span class="sxs-lookup"><span data-stu-id="b96df-112">Examples of operations</span></span>

<span data-ttu-id="b96df-113">Egy gyártó cégnek dolgozik.</span><span class="sxs-lookup"><span data-stu-id="b96df-113">You work for a manufacturing company.</span></span> <span data-ttu-id="b96df-114">Szabálytalanságot hoztak létre és jóváhagyták a minőségi teszten meg nem feleskedő cikkeknél.</span><span class="sxs-lookup"><span data-stu-id="b96df-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="b96df-115">Létrehoztak egy korrekciót, amely azt jelzi, hogy a probléma a gép egy hibás csapágyával volt kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="b96df-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="b96df-116">Az csapágy lecserélését több lépésben kell elvégezni, és a rendszer nyomon követi az egyes műveletek felelősségét.</span><span class="sxs-lookup"><span data-stu-id="b96df-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="b96df-117">Például a következő lépésekre lehet szükség:</span><span class="sxs-lookup"><span data-stu-id="b96df-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="b96df-118">A gyártósor le van állítva, és a tisztítási rutint végzik.</span><span class="sxs-lookup"><span data-stu-id="b96df-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="b96df-119">A karbantartási személyzet lecseréli a csapágyat.</span><span class="sxs-lookup"><span data-stu-id="b96df-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="b96df-120">A minőségbiztosítást végző személyek megvizsgálják a gépet, mielőtt visszakapcsolnák.</span><span class="sxs-lookup"><span data-stu-id="b96df-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="b96df-121">Ebben a példában a következő műveleteket lehet létrehozni az elvégzendő munka megjelölése érdekében:</span><span class="sxs-lookup"><span data-stu-id="b96df-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="b96df-122">A gyártósor leállítása.</span><span class="sxs-lookup"><span data-stu-id="b96df-122">Stop the production line.</span></span>
- <span data-ttu-id="b96df-123">A gyártósor tisztítása.</span><span class="sxs-lookup"><span data-stu-id="b96df-123">Clean out the production line.</span></span>
- <span data-ttu-id="b96df-124">A gép rendszeres karbantartása.</span><span class="sxs-lookup"><span data-stu-id="b96df-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="b96df-125">A gép megvizsgálása.</span><span class="sxs-lookup"><span data-stu-id="b96df-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="b96df-126">Egy művelet létrehozása</span><span class="sxs-lookup"><span data-stu-id="b96df-126">Create an operation</span></span>

1. <span data-ttu-id="b96df-127">Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Műveletek** pontra.</span><span class="sxs-lookup"><span data-stu-id="b96df-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="b96df-128">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="b96df-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b96df-129">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b96df-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b96df-130">**Művelet** – Adja meg a művelet egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="b96df-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="b96df-131">**Leírás** – Adja meg a művelet részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="b96df-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="b96df-132">**Típus** – Ha a művelet csak egy bizonyos típusú rendeléshez kapcsolódó szabálytalanságokkal használható, válassza ki a rendelés típusát (*Beszerzési rendelés* vagy *Értékesítési rendelés*).</span><span class="sxs-lookup"><span data-stu-id="b96df-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="b96df-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b96df-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b96df-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b96df-134">Additional resources</span></span>

- [<span data-ttu-id="b96df-135">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="b96df-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="b96df-136">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b96df-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="b96df-137">Szabálytalanság létrehozása és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="b96df-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="b96df-138">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="b96df-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="b96df-139">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="b96df-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="b96df-140">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="b96df-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="b96df-141">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="b96df-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="b96df-142">A szabálytalanságok problématípusai</span><span class="sxs-lookup"><span data-stu-id="b96df-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="b96df-143">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="b96df-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
