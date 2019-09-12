---
title: Karbantartási dolgozó naptára és ütemezése
description: Ez a témakör a karbantartási dolgozók naptárának és az Eszközkezelőben történő ütemezésnek a kapcsolatát ismerteti.
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
ms.openlocfilehash: 3f86f6475e5226443f5e4d43fb91acafe2afdbb9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887388"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="6e4f8-103">Karbantartási dolgozó naptára és ütemezése</span><span class="sxs-lookup"><span data-stu-id="6e4f8-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="6e4f8-104">A munkarendelések ütemezésekor ütemezést készít a karbantartási dolgozókhoz és az eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="6e4f8-105">A karbantartási dolgozók ütemezésének végrehajtásához minden karbantartási dolgozóhoz be kell állítani egy naptárat.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-105">In order to carry out scheduling on maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="6e4f8-106">A karbantartási dolgozók erőforrásokhoz kapcsolódnak, és az erőforrásokhoz kell munkaidő-naptárakat beállítani.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-106">Maintenance workers are related to a resource, and working time calendars are set up on resoures.</span></span> <span data-ttu-id="6e4f8-107">A dolgozókhoz kapcsolódó naptár és az erőforrás az **Eszközkezelés** > **Beállítás** > **Dolgozók** > **Dolgozók** részen állítható be. A leírás a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című cikkben található.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-107">You set up the resource and calendar related to a worker in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="6e4f8-108">Az alábbi képernyőképen egy, a „Termelés” munkaidőnaptárat használó erőforrással összekapcsolt karbantartási dolgozó látható.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![1. ábra](media/01-work-order-scheduling.png)

<span data-ttu-id="6e4f8-110">Az eszközök naptári beállítására nincs szükség a munkarendelési ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="6e4f8-111">A feltételezés szerint az eszközök egész nap elérhetők a karbantartáshoz.</span><span class="sxs-lookup"><span data-stu-id="6e4f8-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

