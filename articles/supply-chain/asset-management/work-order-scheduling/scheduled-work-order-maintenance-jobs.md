---
title: Ütemezett munkarendelésen kiadott karbantartási feladatok
description: Ez a témakör az Eszközkezelés modul ütemezett munkarendelés-karbantartási feladatait ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b3cc32d6ff263967c1ee843702c28968219ac33
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887182"
---
# <a name="scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="b20f6-103">Ütemezett munkarendelésen kiadott karbantartási feladatok</span><span class="sxs-lookup"><span data-stu-id="b20f6-103">Scheduled work order maintenance jobs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b20f6-104">Az **Ütemezett munkarendelés-karbantartási feladatok** lap segítségével áttekintést kaphat az erőforrásokhoz hozzárendelt munkarendelésekről.</span><span class="sxs-lookup"><span data-stu-id="b20f6-104">The **Scheduled work order maintenance jobs** page is used to get an overview of the work orders allocated to a resource.</span></span> <span data-ttu-id="b20f6-105">A listában az „Emberi erőforrások”, „Eszköz” és „Gép” erőforrástípust használó munkarendelések jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="b20f6-105">Work orders using resource types "Human resources", "Tool", and "Machine" are shown in the list.</span></span> <span data-ttu-id="b20f6-106">A lista használatával áttekintést kaphat az adott erőforráshoz hozzárendelt munkarendelésekről.</span><span class="sxs-lookup"><span data-stu-id="b20f6-106">The list can be used to get an overview of work orders allocated to a specific resource.</span></span> <span data-ttu-id="b20f6-107">A listában gyorsan megtalálhatja azokat a munkarendeléseket is, amelyek egy olyan karbantartási dolgozóhoz vannak hozzárendelve, aki például beteget jelentett reggel, így a feladatot gyorsan egy másik karbantartási dolgozóhoz rendelheti.</span><span class="sxs-lookup"><span data-stu-id="b20f6-107">You can also use it to quickly find a work order allocated to a maintenance worker who, for example, called in sick this morning, and then quickly allocate another maintenance worker to the job.</span></span>

## <a name="view-scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="b20f6-108">Ütemezett munkarendelés-karbantartási feladatok megtekintése</span><span class="sxs-lookup"><span data-stu-id="b20f6-108">View scheduled work order maintenance jobs</span></span>

1. <span data-ttu-id="b20f6-109">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Ütemezett munkarendelés-karbantartási feladatok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b20f6-109">Click **Asset management** > **Common** > **Work orders** > **Scheduled work order maintenance jobs**.</span></span> <span data-ttu-id="b20f6-110">A listájában az összes munkarendelés „Ütemezett” vagy „Folyamatban” életciklus-állapottal látható.</span><span class="sxs-lookup"><span data-stu-id="b20f6-110">You see a list of all work orders set to work order lifecycle state "Scheduled" or "In progress".</span></span>

2. <span data-ttu-id="b20f6-111">A lista például karbantartási dolgozók szerint rendezhető.</span><span class="sxs-lookup"><span data-stu-id="b20f6-111">You can sort the list, for example, by maintenance worker.</span></span> <span data-ttu-id="b20f6-112">A szűrő használatával az egy adott erőforráshoz vagy karbantartási dolgozóhoz rendelt munkarendelések megjelenítendő listáját is korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="b20f6-112">You can also use the filter to limit the list to display work orders allocated to a specific resource or maintenance worker.</span></span>

3. <span data-ttu-id="b20f6-113">A munkarendelésen megtekintheti a megjegyzéseket, és ha szükséges, újakat adhat hozzá, ha kiválasztja a munkarendelési feladatot a listából, és a **Megjegyzések** lehetőségre kattint.</span><span class="sxs-lookup"><span data-stu-id="b20f6-113">You can see notes on the work order and, if required, add new notes by selecting the work order job in the list and clicking **Notes**.</span></span>

4. <span data-ttu-id="b20f6-114">Ha szeretne egy karbantartási dolgozót egy munkarendeléshez hozzárendelni, válassza ki a munkarendelést a listán, majd kattintson a **Munkarendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="b20f6-114">If you want to allocate one maintenance worker to a work order, select the work order in the list, and click **Work order**.</span></span>

5. <span data-ttu-id="b20f6-115">Megnyílik a **Munkarendelés** lap.</span><span class="sxs-lookup"><span data-stu-id="b20f6-115">The **Work order** page opens.</span></span> <span data-ttu-id="b20f6-116">Ha szeretné a munkarendelést egy meghatározott karbantartási dolgozóhoz hozzárendelni, kattintson a **Küldés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b20f6-116">Click **Dispatch** to schedule the work order to a specific maintenance worker.</span></span>

>[!NOTE]
><span data-ttu-id="b20f6-117">Az egy vagy egyszerre több munkarendelés ütemezéséről további információt itt talál: [Munkarendelések ütemezése](../work-order-scheduling/schedule-work-orders.md)és [Munkarendelés elküldése](../work-order-scheduling/dispatch-work-order.md).</span><span class="sxs-lookup"><span data-stu-id="b20f6-117">Read more about scheduling several work orders or one work order in [Schedule work orders](../work-order-scheduling/schedule-work-orders.md) and [Dispatch work order](../work-order-scheduling/dispatch-work-order.md).</span></span>

<span data-ttu-id="b20f6-118">Az alábbi ábrán az **Ütemezett munkarendelés-karbantartási feladatok** lap látható.</span><span class="sxs-lookup"><span data-stu-id="b20f6-118">The figure below shows an example of the **Scheduled work order maintenance jobs** page.</span></span>

![1. ábra](media/07-work-order-scheduling.png)

