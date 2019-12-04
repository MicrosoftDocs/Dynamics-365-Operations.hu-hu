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
ms.openlocfilehash: 44fafe1548f97d8e4a532a17b0ca596320b5e9fb
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814996"
---
# <a name="service-management-overview"></a><span data-ttu-id="252ad-103">Szolgáltatáskezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="252ad-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="252ad-104">Használja a **Szolgáltatáskezelés** lehetőséget a szolgáltatási szerződések és szolgáltatási előfizetések létrehozására, a szolgáltatási rendelésekkel és a vevői kérdések kezelésére és arra, hogy kezelje és elemezze a vevőknek szánt szállítási szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="252ad-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="252ad-105">Szolgáltatási szerződések használatával határozza meg az szervizlátogatás során felhasználat erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="252ad-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="252ad-106">Szolgáltatási szerződések használatával azt is megtekintheti, hogyan kerülnek számlázásra ezek az erőforrások a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="252ad-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="252ad-107">A szolgáltatási szerződés tartalmazhat szolgáltatásiszint-szerződést is, amely megadja a szabványos válaszidőket és eszközöket biztosít a tényleges időt rögzítésére.</span><span class="sxs-lookup"><span data-stu-id="252ad-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="252ad-108">Létrehozhat szervizrendeléseket a szakemberek által a vevő telephelyén tett ütemezett és nem tervezett látogatásokkal kapcsolatos információk kezelésére.</span><span class="sxs-lookup"><span data-stu-id="252ad-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="252ad-109">A szervizrendelések például ilyen adatokat tartalmaznak:</span><span class="sxs-lookup"><span data-stu-id="252ad-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="252ad-110">Munkaórákat, amelyeket a szerviztechnikus el fog végezni</span><span class="sxs-lookup"><span data-stu-id="252ad-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="252ad-111">Szolgáltatás vagy javítás típusát</span><span class="sxs-lookup"><span data-stu-id="252ad-111">The type of service or repair</span></span>

3.  <span data-ttu-id="252ad-112">A javítandó cikk a tünetek és diagnózis részletezésével</span><span class="sxs-lookup"><span data-stu-id="252ad-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="252ad-113">A szolgáltatáshoz vagy javításhoz kapcsolódó minden költség és díj</span><span class="sxs-lookup"><span data-stu-id="252ad-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="252ad-114">Ön megkaphatja, feldolgozhatja és szétoszthatja ezeket a szolgáltatási kérelmeket.</span><span class="sxs-lookup"><span data-stu-id="252ad-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="252ad-115">Miután létrehozta a szervizrendelést a szolgáltatásállapotok segítségével figyelemmel kísérheti annak állapotát, és szabályokat adhat meg, amelyek meghatározzák, hogy milyen műveleteket engedélyezettek az egyes szakaszokban.</span><span class="sxs-lookup"><span data-stu-id="252ad-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="252ad-116">Szervizrendelés befejezésekor láttamozhatja azt, hogy megerősítse annak befejezését és feladhatja a rendelést a számlázás megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="252ad-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="252ad-117">A jelentéskészítő eszközök használatával figyelheti a szervizrendelés árrésit és az előfizetési tranzakciókat, és a munkaleírásokat és munkavégzési elismervényeket nyomtathat.</span><span class="sxs-lookup"><span data-stu-id="252ad-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="252ad-118">Üzleti folyamatok</span><span class="sxs-lookup"><span data-stu-id="252ad-118">Business processes</span></span>

<span data-ttu-id="252ad-119">A következő ábra bemutatja a **Szogáltatáskezelés** magas szintű üzleti folyamatait és megmutatja, hol integrálódnak a szolgáltatási folyamatok más modulokba.</span><span class="sxs-lookup"><span data-stu-id="252ad-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="252ad-120">[![Szolgáltatáskezelés üzleti folyamat ábrája](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="252ad-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="252ad-121">Szolgáltatáskezelés egyetlen pillantással</span><span class="sxs-lookup"><span data-stu-id="252ad-121">Service management at a glance</span></span>

|<span data-ttu-id="252ad-122">Fontos feladatokat</span><span class="sxs-lookup"><span data-stu-id="252ad-122">Important tasks</span></span>           | <span data-ttu-id="252ad-123">Elsődleges lapok</span><span class="sxs-lookup"><span data-stu-id="252ad-123">Primary pages</span></span>                         |<span data-ttu-id="252ad-124">Népszerű jelentések</span><span class="sxs-lookup"><span data-stu-id="252ad-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="252ad-125">Szolgáltatási szerződések teljesítése</span><span class="sxs-lookup"><span data-stu-id="252ad-125">Fulfill service agreements</span></span>|<span data-ttu-id="252ad-126">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="252ad-126">Service agreements</span></span>                     |<span data-ttu-id="252ad-127">Szervizrendelés árrése</span><span class="sxs-lookup"><span data-stu-id="252ad-127">Service order margin</span></span>         |
|<span data-ttu-id="252ad-128">Vevői kérések kezelése</span><span class="sxs-lookup"><span data-stu-id="252ad-128">Handle customer inquiries</span></span> |<span data-ttu-id="252ad-129">Szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="252ad-129">Service orders</span></span>                         |<span data-ttu-id="252ad-130">Munkaleírás</span><span class="sxs-lookup"><span data-stu-id="252ad-130">Work description</span></span>             |
|                          |<span data-ttu-id="252ad-131">Diszpécserközpont</span><span class="sxs-lookup"><span data-stu-id="252ad-131">Dispatch board</span></span>                         |<span data-ttu-id="252ad-132">Tranzakció - előfizetés</span><span class="sxs-lookup"><span data-stu-id="252ad-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="252ad-133">Előfizetési díj tranzakciói</span><span class="sxs-lookup"><span data-stu-id="252ad-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="252ad-134">Szolgáltatáskezelés integrációja</span><span class="sxs-lookup"><span data-stu-id="252ad-134">Integration of Service management</span></span>

<span data-ttu-id="252ad-135">A szolgáltatáskezelés az alábbi modulokkal integrálható:</span><span class="sxs-lookup"><span data-stu-id="252ad-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="252ad-136">Értékesítés és marketing – áttekintés</span><span class="sxs-lookup"><span data-stu-id="252ad-136">Sales and marketing overview</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="252ad-137">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="252ad-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

