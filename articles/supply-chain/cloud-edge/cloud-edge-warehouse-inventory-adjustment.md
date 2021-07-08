---
title: Raktárkészlet helyesbítése
description: Ez a témakör a raktári készletkorrekciós naplóról és a skálázási egység használata esetén történő feldolgozásról nyújt tájékoztatást.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1bf147ce430d84980516d8d4824081ee2a9321a2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271232"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="aede9-103">Raktárkészlet helyesbítése</span><span class="sxs-lookup"><span data-stu-id="aede9-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aede9-104">A Raktárkészlet-korrekció funkció a felhő- és peremalapú skálázási egységek futtatásakor használatos a [gyártási munkaterhelések](cloud-edge-workload-manufacturing.md) és a [raktárkezelési munkaterhelések](cloud-edge-workload-warehousing.md) során.</span><span class="sxs-lookup"><span data-stu-id="aede9-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="aede9-105">Ha egy dolgozó a raktári alkalmazás segítségével végez készletkorrekciót a skálázási egység raktárkezelési munkaterhelése alapján, a tényleges aktuális készlet frissítését a **Raktárkészlet-korrekciós napló** kötegelt feladattal kell feldolgozni, amelyet a következő helyen futtathat és ütemezhet: **Raktárkezelés > Időszakos feladatok > Raktárkészlet-korrekciós napló**.</span><span class="sxs-lookup"><span data-stu-id="aede9-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="aede9-106">A raktári alkalmazás következő munkafolyamatai jelenleg a **Raktárkészlet-korrekciós naplót** használják a skálázási egység munkaterhelésein:</span><span class="sxs-lookup"><span data-stu-id="aede9-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="aede9-107">Korrekció be/ki</span><span class="sxs-lookup"><span data-stu-id="aede9-107">Adjustment in/out</span></span>
- <span data-ttu-id="aede9-108">Ciklikus leltározás</span><span class="sxs-lookup"><span data-stu-id="aede9-108">Cycle counting</span></span>
- <span data-ttu-id="aede9-109">Azonosítótábla rakodása</span><span class="sxs-lookup"><span data-stu-id="aede9-109">License plate loading</span></span>

<span data-ttu-id="aede9-110">Számos készlettranzakció jön létre a készletkorrekciós folyamat során, mivel a központ és a skálázási egységek telepítése osztoznak a készletrekordokon.</span><span class="sxs-lookup"><span data-stu-id="aede9-110">Several inventory transactions are created as part of each inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="aede9-111">Készletkorrekció - példa</span><span class="sxs-lookup"><span data-stu-id="aede9-111">Inventory adjustment example</span></span>

<span data-ttu-id="aede9-112">Ebben a példában egy raktári dolgozó a raktári alkalmazást használta az aktuális készlet hozzáadásának regisztrálásakor.</span><span class="sxs-lookup"><span data-stu-id="aede9-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="aede9-113">Először a skálázási egység munkaterhelése létrehoz egy raktárkészlet-korrekciós tranzakciót a pozitív fizikai korrekcióhoz, amelyet ezután szinkronizál a központtal, és ez az aktuális készlet növekedését eredményezi a központon.</span><span class="sxs-lookup"><span data-stu-id="aede9-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="aede9-114">Típus</span><span class="sxs-lookup"><span data-stu-id="aede9-114">Type</span></span>                                    | <span data-ttu-id="aede9-115">Skálázási egység</span><span class="sxs-lookup"><span data-stu-id="aede9-115">Scale unit</span></span> | <span data-ttu-id="aede9-116">Irány</span><span class="sxs-lookup"><span data-stu-id="aede9-116">Direction</span></span> | <span data-ttu-id="aede9-117">Központ</span><span class="sxs-lookup"><span data-stu-id="aede9-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="aede9-118">Raktárkészlet helyesbítése</span><span class="sxs-lookup"><span data-stu-id="aede9-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="aede9-119">+1</span><span class="sxs-lookup"><span data-stu-id="aede9-119">+1</span></span>         | ->        | <span data-ttu-id="aede9-120">+1</span><span class="sxs-lookup"><span data-stu-id="aede9-120">+1</span></span>  |

<span data-ttu-id="aede9-121">A központ ezután feldolgoz egy leltárnapló-feladást, amely az [üzenetfeldolgozó üzenetei](cloud-edge-message-processor-messages.md) révén érkezik meg.</span><span class="sxs-lookup"><span data-stu-id="aede9-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="aede9-122">Ezzel frissíti a további aktuális készletet.</span><span class="sxs-lookup"><span data-stu-id="aede9-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="aede9-123">A dupla aktuális készlet megakadályozása érdekében a központ létrehoz egy ellentranzakciót a folyamat részeként, és eltávolítja a raktárkészlet-korrekcióhoz kapcsolódó, korábban rögzített aktuális készletet.</span><span class="sxs-lookup"><span data-stu-id="aede9-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="aede9-124">Típus</span><span class="sxs-lookup"><span data-stu-id="aede9-124">Type</span></span>                                    | <span data-ttu-id="aede9-125">Skálázási egység</span><span class="sxs-lookup"><span data-stu-id="aede9-125">Scale unit</span></span> | <span data-ttu-id="aede9-126">Irány</span><span class="sxs-lookup"><span data-stu-id="aede9-126">Direction</span></span> | <span data-ttu-id="aede9-127">Központ</span><span class="sxs-lookup"><span data-stu-id="aede9-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="aede9-128">Leltár</span><span class="sxs-lookup"><span data-stu-id="aede9-128">Counting</span></span>                                | <span data-ttu-id="aede9-129">+1</span><span class="sxs-lookup"><span data-stu-id="aede9-129">+1</span></span>         | <-        | <span data-ttu-id="aede9-130">+1</span><span class="sxs-lookup"><span data-stu-id="aede9-130">+1</span></span>  |
| <span data-ttu-id="aede9-131">Raktárkészlet-korrekció (ellenszámla)</span><span class="sxs-lookup"><span data-stu-id="aede9-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="aede9-132">-1</span><span class="sxs-lookup"><span data-stu-id="aede9-132">-1</span></span>         | <-        | <span data-ttu-id="aede9-133">-1</span><span class="sxs-lookup"><span data-stu-id="aede9-133">-1</span></span>  |

<span data-ttu-id="aede9-134">Miután a skálázási egység létrehozta a **Raktárkészlet-korrekciós naplót** a központban, mind a **Leltárnaplót** és az **Ellenszámlanaplót** is áttekintheti, amelyeket a központ a helyesbítési folyamat részeként hoz létre.</span><span class="sxs-lookup"><span data-stu-id="aede9-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="aede9-135">A Supply Chain Managementben ezeket a naplóbejegyzéseket és tranzakciókat a következő lépésekkel lehet áttekintheti:</span><span class="sxs-lookup"><span data-stu-id="aede9-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="aede9-136">Jelentkezzen be a skálázási egységbe.</span><span class="sxs-lookup"><span data-stu-id="aede9-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="aede9-137">Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktárkészlet-korrekciós napló** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="aede9-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="aede9-138">A **Raktárkészlet-korrekciós napló** oldalon keresse meg és nyissa meg azt a naplót, amely rögzítette az aktuális készlet változását.</span><span class="sxs-lookup"><span data-stu-id="aede9-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="aede9-139">A **Naplósorok** szakasz az e naplóval rögzített minden egyes módosítást megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="aede9-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="aede9-140">Jelentkezzen be a központba.</span><span class="sxs-lookup"><span data-stu-id="aede9-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="aede9-141">Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktárkészlet-korrekciós napló** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="aede9-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="aede9-142">A **Raktárkészlet-korrekciós napló** oldalon ekkor látnia kell ugyanazt a naplót, ha szinkronizálta a központot és a skálázási egységet.</span><span class="sxs-lookup"><span data-stu-id="aede9-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="aede9-143">Nyissa meg a naplót.</span><span class="sxs-lookup"><span data-stu-id="aede9-143">Open the journal.</span></span> <span data-ttu-id="aede9-144">Ha az [üzenetfeldolgozó üzeneteit](cloud-edge-message-processor-messages.md) feldolgozták, a fejlécben a **Leltárnaplóra** és az **Ellenszámlanaplóra** mutató hivatkozások jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="aede9-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="aede9-145">A **Leltárnaplónak** a naplósorokkal azonos dimenzióértékeket kell mutatnia.</span><span class="sxs-lookup"><span data-stu-id="aede9-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="aede9-146">Az **Ellenszámlanaplónak** az ellenszámlát kell megjelenítenie, amely eltávolítja a dupla készletkorrekciót.</span><span class="sxs-lookup"><span data-stu-id="aede9-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="aede9-147">Amikor minden szinkronizálás és feldolgozás befejeződött, a **Leltárnapló** és az **Ellenszámlanapló** szinkronizálva lesz a skálázási egységgel.</span><span class="sxs-lookup"><span data-stu-id="aede9-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="aede9-148">Ezek a **Raktárkészlet-korrekciós napló** megfelelő lapján is megtekinthetők.</span><span class="sxs-lookup"><span data-stu-id="aede9-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
