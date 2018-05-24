---
title: "Szolgáltatáskezelés"
description: "Használja a Szolgáltatáskezelés lehetőséget a szolgáltatási szerződések és szolgáltatási előfizetések létrehozására, a szolgáltatási rendelésekkel és a vevői kérdések kezelésére és arra, hogy kezelje és elemezze a vevőknek szánt szállítási szolgáltatásokat."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="e8023-103">Szolgáltatáskezelés</span><span class="sxs-lookup"><span data-stu-id="e8023-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e8023-104">Használja a **Szolgáltatáskezelés** lehetőséget a szolgáltatási szerződések és szolgáltatási előfizetések létrehozására, a szolgáltatási rendelésekkel és a vevői kérdések kezelésére és arra, hogy kezelje és elemezze a vevőknek szánt szállítási szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="e8023-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="e8023-105">Szolgáltatási szerződések használatával határozza meg az szervizlátogatás során felhasználat erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="e8023-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="e8023-106">Szolgáltatási szerződések használatával azt is megtekintheti, hogyan kerülnek számlázásra ezek az erőforrások a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="e8023-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="e8023-107">A szolgáltatási szerződés tartalmazhat szolgáltatásiszint-szerződést is, amely megadja a szabványos válaszidőket és eszközöket biztosít a tényleges időt rögzítésére.</span><span class="sxs-lookup"><span data-stu-id="e8023-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="e8023-108">Létrehozhat szervizrendeléseket a szakemberek által a vevő telephelyén tett ütemezett és nem tervezett látogatásokkal kapcsolatos információk kezelésére.</span><span class="sxs-lookup"><span data-stu-id="e8023-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="e8023-109">A szervizrendelések például ilyen adatokat tartalmaznak:</span><span class="sxs-lookup"><span data-stu-id="e8023-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="e8023-110">Munkaórákat, amelyeket a szerviztechnikus el fog végezni</span><span class="sxs-lookup"><span data-stu-id="e8023-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="e8023-111">Szolgáltatás vagy javítás típusát</span><span class="sxs-lookup"><span data-stu-id="e8023-111">The type of service or repair</span></span>

3.  <span data-ttu-id="e8023-112">A javítandó cikk a tünetek és diagnózis részletezésével</span><span class="sxs-lookup"><span data-stu-id="e8023-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="e8023-113">A szolgáltatáshoz vagy javításhoz kapcsolódó minden költség és díj</span><span class="sxs-lookup"><span data-stu-id="e8023-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="e8023-114">Vevők az interneten keresztül küldhetnek be szervízkérelmeket az Enterprise Portal használatával.</span><span class="sxs-lookup"><span data-stu-id="e8023-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="e8023-115">Ön megkaphatja, feldolgozhatja és szétoszthatja ezeket a kérelmeket.</span><span class="sxs-lookup"><span data-stu-id="e8023-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="e8023-116">Miután létrehozta a szervizrendelést a szolgáltatásállapotok segítségével figyelemmel kísérheti annak állapotát, és szabályokat adhat meg, amelyek meghatározzák, hogy milyen műveleteket engedélyezettek az egyes szakaszokban.</span><span class="sxs-lookup"><span data-stu-id="e8023-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="e8023-117">Szervizrendelés befejezésekor láttamozhatja azt, hogy megerősítse annak befejezését és feladhatja a rendelést a számlázás megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="e8023-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="e8023-118">A jelentéskészítő eszközök használatával figyelheti a szervizrendelés árrésit és az előfizetési tranzakciókat, és a munkaleírásokat és munkavégzési elismervényeket nyomtathat.</span><span class="sxs-lookup"><span data-stu-id="e8023-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="e8023-119">Üzleti folyamatok</span><span class="sxs-lookup"><span data-stu-id="e8023-119">Business processes</span></span>

<span data-ttu-id="e8023-120">A következő ábra bemutatja a **Szolgáltatáskezelés** magas szintű üzleti folyamatait, és megmutatja, hogy a szolgáltatási folyamatok hol integrálódnak a Microsoft Dynamics 365 for Finance and Operations más moduljaival.</span><span class="sxs-lookup"><span data-stu-id="e8023-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="e8023-121">[![Szolgáltatáskezelés üzleti folyamat ábrája](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="e8023-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="e8023-122">Szolgáltatáskezelés egyetlen pillantással</span><span class="sxs-lookup"><span data-stu-id="e8023-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e8023-123">Fontos feladatokat</span><span class="sxs-lookup"><span data-stu-id="e8023-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="e8023-124">Alapanyagok</span><span class="sxs-lookup"><span data-stu-id="e8023-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="e8023-125">Népszerű jelentések</span><span class="sxs-lookup"><span data-stu-id="e8023-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8023-126">Szolgáltatási szerződések teljesítése</span><span class="sxs-lookup"><span data-stu-id="e8023-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="e8023-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Szolgáltatási szerződések (képernyő)</a></span><span class="sxs-lookup"><span data-stu-id="e8023-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="e8023-128"><strong>Szervizrendelés árrése</strong></span><span class="sxs-lookup"><span data-stu-id="e8023-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8023-129">Vevői kérések kezelése</span><span class="sxs-lookup"><span data-stu-id="e8023-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="e8023-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Szervizrendelések (képernyő)</a></span><span class="sxs-lookup"><span data-stu-id="e8023-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="e8023-131"><strong>Munkaleírás</strong></span><span class="sxs-lookup"><span data-stu-id="e8023-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e8023-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Diszpécserközpont (képernyő)</a></span><span class="sxs-lookup"><span data-stu-id="e8023-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="e8023-133"><strong>Tranzakció - előfizetés</strong></span><span class="sxs-lookup"><span data-stu-id="e8023-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e8023-134"><strong>Előfizetési díj tranzakciói</strong></span><span class="sxs-lookup"><span data-stu-id="e8023-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="e8023-135">Szolgáltatáskezelés integrációja</span><span class="sxs-lookup"><span data-stu-id="e8023-135">Integration of Service management</span></span>

<span data-ttu-id="e8023-136">A szolgáltatáskezelés a következő Microsoft Dynamics 365 for Finance and Operations modulokkal integrálható:</span><span class="sxs-lookup"><span data-stu-id="e8023-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="e8023-137">Értékesítés és marketing</span><span class="sxs-lookup"><span data-stu-id="e8023-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="e8023-138">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="e8023-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


