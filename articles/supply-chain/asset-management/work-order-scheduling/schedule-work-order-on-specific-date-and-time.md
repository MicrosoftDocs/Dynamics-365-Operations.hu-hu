---
title: Munkarendelés ütemezése megadott dátumra és időpontra
description: Ez a témakör azt mutatja be, hogyan lehet munkarendelést ütemezni egy adott dátumra és időpontra az Eszközkezelés modulban.
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
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887365"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="68e81-103">Munkarendelés ütemezése megadott dátumra és időpontra</span><span class="sxs-lookup"><span data-stu-id="68e81-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="68e81-104">Ha egy munkarendelést meghatározott napon *és* időpontban kell ütemezni, felülbírálhatja az alap ütemezési folyamatot az Eszközkezelés modulban, és létrehozhat egy meghatározott ütemezést a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="68e81-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="68e81-105">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="68e81-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="68e81-106">A munkarendelés listán kattintson a munkarendelés azonosítójára a **Munkarendelés** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="68e81-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="68e81-107">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="68e81-107">Click **Edit**.</span></span>

4. <span data-ttu-id="68e81-108">A **Munkarendelés fejléce** gyorslapon adja meg a kezdő és záró dátumot a **Várható kezdés** és a **Várható befejezés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="68e81-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

![1. ábra](media/05-work-order-scheduling.png)

5. <span data-ttu-id="68e81-110">Az **Általános** lapon kattintson az **Ütemezés** elemre a szokásos ütemezési folyamat használatához, vagy kattintson a **Küldés** gombra, ha a munkarendelést egy adott dolgozóhoz szeretné ütemezni.</span><span class="sxs-lookup"><span data-stu-id="68e81-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to schedule the work order to a specific worker.</span></span>

6. <span data-ttu-id="68e81-111">Ha szeretné felülírni a meglévő kapacitásfoglalásokat annak érdekében, hogy a munkarendelést a várható időszakra ütemezze a program, az alábbi ábrán látható módon végezze el az elemek kiválasztását a **Munkarendelés ütemezése** párbeszédablakon > a **Véges kapacitás** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="68e81-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="68e81-112">Ez azt jelenti, hogy az ütemezési folyamat figyelmen kívül hagyja a meglévő kapacitásfoglalásokat, mert a munkarendelésnek a várható időpontban kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="68e81-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

![2. ábra](media/06-work-order-scheduling.png)

7. <span data-ttu-id="68e81-114">Az ütemezés megkezdéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="68e81-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="68e81-115">Ha az ütemezési folyamat dupla foglalást eredményez, akkor üzenet jelenik meg a képernyőn, és módosíthatja a kapcsolódó munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="68e81-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="68e81-116">A karbantartási dolgozót akkor tudja a munkarendeléshez ütemezni, ha elérhető a várt kezdő dátumon és időpontban.</span><span class="sxs-lookup"><span data-stu-id="68e81-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="68e81-117">A  dolgozó elérhetősége beállítás itt érhető el: [Dolgozó naptára](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="68e81-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

