---
title: Szolgáltatáskezelés áttekintése
description: Használja a Szolgáltatáskezelés lehetőséget a szolgáltatási szerződések és szolgáltatási előfizetések létrehozására, a szolgáltatási rendelésekkel és a vevői kérdések kezelésére és arra, hogy kezelje és elemezze a vevőknek szánt szállítási szolgáltatásokat.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20751acfc012e2ac1eef99c778c5b0353baf1827
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865849"
---
# <a name="service-management-overview"></a><span data-ttu-id="cf3fc-103">Szolgáltatáskezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="cf3fc-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="cf3fc-104">Használja a **Szolgáltatáskezelés** lehetőséget a szolgáltatási szerződések és szolgáltatási előfizetések létrehozására, a szolgáltatási rendelésekkel és a vevői kérdések kezelésére és arra, hogy kezelje és elemezze a vevőknek szánt szállítási szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="cf3fc-105">Szolgáltatási szerződések használatával határozza meg az szervizlátogatás során felhasználat erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="cf3fc-106">Szolgáltatási szerződések használatával azt is megtekintheti, hogyan kerülnek számlázásra ezek az erőforrások a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="cf3fc-107">A szolgáltatási szerződés tartalmazhat szolgáltatásiszint-szerződést is, amely megadja a szabványos válaszidőket és eszközöket biztosít a tényleges időt rögzítésére.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="cf3fc-108">Létrehozhat szervizrendeléseket a szakemberek által a vevő telephelyén tett ütemezett és nem tervezett látogatásokkal kapcsolatos információk kezelésére.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="cf3fc-109">A szervizrendelések például ilyen adatokat tartalmaznak:</span><span class="sxs-lookup"><span data-stu-id="cf3fc-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="cf3fc-110">Munkaórákat, amelyeket a szerviztechnikus el fog végezni</span><span class="sxs-lookup"><span data-stu-id="cf3fc-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="cf3fc-111">Szolgáltatás vagy javítás típusát</span><span class="sxs-lookup"><span data-stu-id="cf3fc-111">The type of service or repair</span></span>

3.  <span data-ttu-id="cf3fc-112">A javítandó cikk a tünetek és diagnózis részletezésével</span><span class="sxs-lookup"><span data-stu-id="cf3fc-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="cf3fc-113">A szolgáltatáshoz vagy javításhoz kapcsolódó minden költség és díj</span><span class="sxs-lookup"><span data-stu-id="cf3fc-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="cf3fc-114">Ön megkaphatja, feldolgozhatja és szétoszthatja ezeket a szolgáltatási kérelmeket.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="cf3fc-115">Miután létrehozta a szervizrendelést a szolgáltatásállapotok segítségével figyelemmel kísérheti annak állapotát, és szabályokat adhat meg, amelyek meghatározzák, hogy milyen műveleteket engedélyezettek az egyes szakaszokban.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="cf3fc-116">Szervizrendelés befejezésekor láttamozhatja azt, hogy megerősítse annak befejezését és feladhatja a rendelést a számlázás megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="cf3fc-117">A jelentéskészítő eszközök használatával figyelheti a szervizrendelés árrésit és az előfizetési tranzakciókat, és a munkaleírásokat és munkavégzési elismervényeket nyomtathat.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="cf3fc-118">Üzleti folyamatok</span><span class="sxs-lookup"><span data-stu-id="cf3fc-118">Business processes</span></span>

<span data-ttu-id="cf3fc-119">A következő ábra bemutatja a **Szogáltatáskezelés** magas szintű üzleti folyamatait és megmutatja, hol integrálódnak az szolgáltatási folyamatok más modulokba a Microsoft Dynamics 365 for Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="cf3fc-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="cf3fc-120">[![Szolgáltatáskezelés üzleti folyamat ábrája](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="cf3fc-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="cf3fc-121">Szolgáltatáskezelés egyetlen pillantással</span><span class="sxs-lookup"><span data-stu-id="cf3fc-121">Service management at a glance</span></span>

|<span data-ttu-id="cf3fc-122">Fontos feladatokat</span><span class="sxs-lookup"><span data-stu-id="cf3fc-122">Important tasks</span></span>           | <span data-ttu-id="cf3fc-123">Elsődleges lapok</span><span class="sxs-lookup"><span data-stu-id="cf3fc-123">Primary pages</span></span>                         |<span data-ttu-id="cf3fc-124">Népszerű jelentések</span><span class="sxs-lookup"><span data-stu-id="cf3fc-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="cf3fc-125">Szolgáltatási szerződések teljesítése</span><span class="sxs-lookup"><span data-stu-id="cf3fc-125">Fulfill service agreements</span></span>|<span data-ttu-id="cf3fc-126">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="cf3fc-126">Service agreements</span></span>                     |<span data-ttu-id="cf3fc-127">Szervizrendelés árrése</span><span class="sxs-lookup"><span data-stu-id="cf3fc-127">Service order margin</span></span>         |
|<span data-ttu-id="cf3fc-128">Vevői kérések kezelése</span><span class="sxs-lookup"><span data-stu-id="cf3fc-128">Handle customer inquiries</span></span> |<span data-ttu-id="cf3fc-129">Szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="cf3fc-129">Service orders</span></span>                         |<span data-ttu-id="cf3fc-130">Munkaleírás</span><span class="sxs-lookup"><span data-stu-id="cf3fc-130">Work description</span></span>             |
|                          |<span data-ttu-id="cf3fc-131">Diszpécserközpont</span><span class="sxs-lookup"><span data-stu-id="cf3fc-131">Dispatch board</span></span>                         |<span data-ttu-id="cf3fc-132">Tranzakció - előfizetés</span><span class="sxs-lookup"><span data-stu-id="cf3fc-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="cf3fc-133">Előfizetési díj tranzakciói</span><span class="sxs-lookup"><span data-stu-id="cf3fc-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="cf3fc-134">Szolgáltatáskezelés integrációja</span><span class="sxs-lookup"><span data-stu-id="cf3fc-134">Integration of Service management</span></span>

<span data-ttu-id="cf3fc-135">A szolgáltatáskezelés az alábbi modulokkal integrálható:</span><span class="sxs-lookup"><span data-stu-id="cf3fc-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="cf3fc-136">Értékesítés és marketing</span><span class="sxs-lookup"><span data-stu-id="cf3fc-136">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="cf3fc-137">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="cf3fc-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

