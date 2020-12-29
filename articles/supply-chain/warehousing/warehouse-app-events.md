---
title: Raktári alkalmazás eseményei
description: Ez a témakör a raktári alkalmazáson belüli események feldolgozását mutatja be, melyet a raktári alkalmazás eseményüzeneteinek egy kötegelt feladat részeként való feldolgozására használhatnak.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 210008c4a1366773f465c59b38eca30f11f0b38c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429379"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="99872-103">Raktári alkalmazás eseményeinek feldolgozása</span><span class="sxs-lookup"><span data-stu-id="99872-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99872-104">A Supply Chain Management modulban futtatott kötegelt feladatok felhasználhatják a raktári alkalmazás által kiadott feldolgozási eseményekhez küldött várólistához tartozó adatokat annak érdekében, hogy a jelzett eseményekre szükséges módon lehessen reagálni.</span><span class="sxs-lookup"><span data-stu-id="99872-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="99872-105">Ez a funkció a dolgozók által, az alkalmazással végrehajtott bizonyos művelettípusokra válaszul megfelelő eseményeket adnak a várólistához.</span><span class="sxs-lookup"><span data-stu-id="99872-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="99872-106">Ez történik például akkor, amikor a **Raktári alkalmazásból átmozgatási rendelések létrehozása és feldolgozása** funkciót használják, és az átmozgatási rendelés fejléce és sorai a háttérben jönnek létre és frissülnek, mialatt a rendszer a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="99872-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="99872-107">A Raktári alkalmazás eseményeinek feldolgozása funkció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="99872-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="99872-108">A funkció használata előtt engedélyeznie kell a saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="99872-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="99872-109">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="99872-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="99872-110">A Raktári alkalmazás eseményeinek feldolgozása funkció a következő felsorolásban szerepel:</span><span class="sxs-lookup"><span data-stu-id="99872-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="99872-111">**Modul:** Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="99872-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="99872-112">**Funkció neve** – Raktári alkalmazás eseményeinek feldolgozása</span><span class="sxs-lookup"><span data-stu-id="99872-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="99872-113">Kötegelt feladat létrehozása a raktári alkalmazás eseményeinek feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="99872-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="99872-114">Raktári alkalmazás eseményeinek feldolgozása</span><span class="sxs-lookup"><span data-stu-id="99872-114">Process warehouse app events</span></span>

<span data-ttu-id="99872-115">Ütemezett kötegelt feladat beállítása a raktári alkalmazás eseményeinek feldolgozásához, az átmozgatási rendelés létrehozása és sor frissítése céljából.</span><span class="sxs-lookup"><span data-stu-id="99872-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="99872-116">Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktári alkalmazás eseményeinek feldolgozása** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="99872-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="99872-117">Megjelenik a Raktári alkalmazás eseményeinek feldolgozása párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="99872-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="99872-118">Nyissa meg a **Futtatás a háttérben** gyorslapot, majd állítsa a **Kötegelt feldolgozást** **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="99872-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="99872-119">A **Futtatás a háttérben** gyorslapon válassz az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="99872-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="99872-120">Megnyílik az **Ismétlődés meghatározása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="99872-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="99872-121">Az üzleti tevékenységének megfelelően állítsa be a futási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="99872-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="99872-122">Az **OK** gomb kiválasztásával visszatérhet a **Raktári alkalmazás eseményeinek feldolgozása** párbeszédpanelhez.</span><span class="sxs-lookup"><span data-stu-id="99872-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="99872-123">Válassza az **OK** gombot a **Raktári alkalmazás eseményeinek feldolgozása** párbeszédpanelen a kötegelt feladat kötegelt várólistájához adásához.</span><span class="sxs-lookup"><span data-stu-id="99872-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="99872-124">A raktári alkalmazás eseményeinek lekérdezése</span><span class="sxs-lookup"><span data-stu-id="99872-124">Query warehouse app events</span></span>

<span data-ttu-id="99872-125">A raktári alkalmazás által létrehozott esemény-várólistát és eseményüzeneteket a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszköznaplók \> Raktári alkalmazás eseményei** menüpontba lépve tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="99872-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="99872-126">A szokásos esemény-várólista folyamata</span><span class="sxs-lookup"><span data-stu-id="99872-126">The standard event queue process</span></span>

<span data-ttu-id="99872-127">A raktári alkalmazások eseményeinek várólistája általában a következő folyamatban használható:</span><span class="sxs-lookup"><span data-stu-id="99872-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="99872-128">Egy esemény jelenik meg a várólistán egy eseményüzenettel.</span><span class="sxs-lookup"><span data-stu-id="99872-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="99872-129">Az új üzenet kezdetben **Várakozó** eseményállapottal rendelkezik, amely azt jelenti, hogy a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladat nem veszi fel és dolgozza fel ezt az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="99872-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="99872-130">Amint az üzenet **Várólistán** állapotra vált át, a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladat felveszi és feldolgozza az eseményt.</span><span class="sxs-lookup"><span data-stu-id="99872-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="99872-131">A kötegelt feladat az eseményállapotokat **Befejezett** vagy **Sikertelen** állapotra változtatja attól függően, hogy a kért folyamat végrehajtható volt-e.</span><span class="sxs-lookup"><span data-stu-id="99872-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="99872-132">Amikor az összes kapcsolódó eseményüzenet **Befejezett** állapotra vált át, a program törli az eseményt a várólistából.</span><span class="sxs-lookup"><span data-stu-id="99872-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="99872-133">Részletesebb példáért lásd: [Átmozgatási rendelés létrehozása a raktári alkalmazás folyamatából](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="99872-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="99872-134">Eseményhibák kezelése</span><span class="sxs-lookup"><span data-stu-id="99872-134">Handle event errors</span></span>

<span data-ttu-id="99872-135">A raktári események feldolgozása részeként a kért üzenettevékenység nem kaphat folyamatot a kötegelt feladatból.</span><span class="sxs-lookup"><span data-stu-id="99872-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="99872-136">Ebben az esetben az eseményüzenet **Sikertelen** állapotra vált át.</span><span class="sxs-lookup"><span data-stu-id="99872-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="99872-137">A **Kötegnapló** adataival megtudhatja, hogy miért és milyen lépéseket kell tenni a problémák orvoslására.</span><span class="sxs-lookup"><span data-stu-id="99872-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="99872-138">Részletesebb példáért lásd: [Átmozgatási rendelés létrehozása a raktári alkalmazásból](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="99872-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="99872-139">Sikertelen raktári alkalmazáson belüli eseményüzenet alaphelyzetbe állítása:</span><span class="sxs-lookup"><span data-stu-id="99872-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="99872-140">Lépjen a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszközök naplói \> Raktári alkalmazás eseményei** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="99872-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="99872-141">A **Raktári alkalmazás eseményüzenetei** gyorsfülön megkeresheti és kiválaszthatja azt a kapcsolódó eseményt, amely **Sikertelen** állapotot mutat az **Eseményállapot** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="99872-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="99872-142">Válassza ki az **Alaphelyzetbe állítás** elemet a **Raktári alkalmazás eseményüzenetei** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="99872-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="99872-143">Folytassa a munkát mindaddig, amíg az összes fontos üzenetet alaphelyzetbe nem állítja.</span><span class="sxs-lookup"><span data-stu-id="99872-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="99872-144">A **Sikertelen** eseményüzenetet a **Raktári alkalmazás eseményüzenetei eszköztár** **Törlés** opciójával is el lehet távolítani.</span><span class="sxs-lookup"><span data-stu-id="99872-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>
