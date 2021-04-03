---
title: Szolgáltatási szerződések kialakítása és megkötése – áttekintés
description: A szolgáltatási szerződések segítségével meghatározhatja, hogy milyen erőforrásokat használ egy átlagos szervizlátogatás során, és ezeket hogyan számlázza a vevőnek.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86855e8893cdf5d6e53cb34465480ade06a6da95
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258494"
---
# <a name="develop-and-establish-service-agreements-overview"></a><span data-ttu-id="42efb-103">Szolgáltatási szerződések kialakítása és megkötése – áttekintés</span><span class="sxs-lookup"><span data-stu-id="42efb-103">Develop and establish service agreements overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42efb-104">A szolgáltatási szerződések segítségével meghatározhatja, hogy milyen erőforrásokat használ egy átlagos szervizlátogatás során, és ezeket hogyan számlázza a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="42efb-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="42efb-105">Minden szolgáltatási szerződés projektekhez van csatolva, amelyeken keresztül feladhatók és kiszámlázhatók a tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="42efb-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="42efb-106">A szervizrendelési tranzakciók ugyanakkor közvetlenül a projekten keresztül is kiszámlázhatók, anélkül, hogy a szervizrendelést szolgáltatási szerződéshez kellene csatolniuk.</span><span class="sxs-lookup"><span data-stu-id="42efb-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="42efb-107">Ha a szervizrendelés csak egyszeri szervizlátogatás miatt jött létre, akkor érdemes ezt az utat választani, mivel a szerviztranzakció feldolgozása így kevesebb erőforrást emészt fel, mint a részletes szolgáltatási szerződési adatok hosszabb ideig tartó nyilvántartása az ügyfélről.</span><span class="sxs-lookup"><span data-stu-id="42efb-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="42efb-108">Szolgáltatási szerződés</span><span class="sxs-lookup"><span data-stu-id="42efb-108">Service agreement</span></span>

<span data-ttu-id="42efb-109">Minden szolgáltatási szerződésben meg kell adnia egy projektet, a szolgáltatási szerződés azonosítóját és szerződéscsoportját.</span><span class="sxs-lookup"><span data-stu-id="42efb-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="42efb-110">A szolgáltatási szerződések csoportjai a szolgáltatási szerződések rendezésére és csoportosítására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="42efb-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="42efb-111">A szolgáltatási szerződés fejlécének egyes beállításai a csatolt szerződéssorokra vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="42efb-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="42efb-112">A szolgáltatási szerződés felfüggesztési állapota.</span><span class="sxs-lookup"><span data-stu-id="42efb-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="42efb-113">Ha a szolgáltatási szerződés fel van függesztve, akkor nem lehet belőle szervizrendeléseket generálni.</span><span class="sxs-lookup"><span data-stu-id="42efb-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="42efb-114">A szolgáltatási szerződés időtartama.</span><span class="sxs-lookup"><span data-stu-id="42efb-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="42efb-115">A szervizrendeléssorok hogyan állnak össze szervizrendelésekké.</span><span class="sxs-lookup"><span data-stu-id="42efb-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="42efb-116">A szolgáltatási szerződés sablon-e.</span><span class="sxs-lookup"><span data-stu-id="42efb-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="42efb-117">A szolgáltatási szerződés fejlécében beállíthatja azokat a szolgáltatási tárgyakat és szervizfeladatokat is, amelyek a szerződében használhatók. Adja meg azokat a szervizfeladatokat és -tárgyakat, amelyeket a szerződés különböző soraihoz kell majd csatolni.</span><span class="sxs-lookup"><span data-stu-id="42efb-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="42efb-118">A szolgáltatási szerződés fejlécéből szerződéssorokat illetve szolgáltatássablon-sorokat másolhat az aktuális szolgáltatási szerződésbe.</span><span class="sxs-lookup"><span data-stu-id="42efb-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="42efb-119">A programban felfüggesztheti a szolgáltatási szerződéseket, és leállíthatja az egyes szolgáltatásiszerződés-sorokat.</span><span class="sxs-lookup"><span data-stu-id="42efb-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="42efb-120">Ha valamelyik szolgáltatásiszerződés-sornál bejelöli a **Felfüggesztve** jelölőnégyzetet, akkor a következők nem lehetségesek:</span><span class="sxs-lookup"><span data-stu-id="42efb-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="42efb-121">Szervizrendelések automatikus és kézi létrehozása a szolgáltatási szerződésből.</span><span class="sxs-lookup"><span data-stu-id="42efb-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="42efb-122">Ha valamelyik szolgáltatásiszerződés-sornál bejelöli a **Leállítva** jelölőnégyzetet, akkor a következők nem lehetségesek:</span><span class="sxs-lookup"><span data-stu-id="42efb-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="42efb-123">Szervizrendelések automatikus és kézi létrehozása a szolgáltatásiszerződés-sorból.</span><span class="sxs-lookup"><span data-stu-id="42efb-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="42efb-124">A szolgáltatásiszerződés-sor másolása egy másik szolgáltatási szerződésbe vagy szervizrendelésbe.</span><span class="sxs-lookup"><span data-stu-id="42efb-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="42efb-125">Ha egy szolgáltatási szerződés fel van függesztve, akkor a program minden hozzá tartozó sort leállít, függetlenül attól, hogy a sor milyen állapotban van.</span><span class="sxs-lookup"><span data-stu-id="42efb-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="42efb-126">Szolgáltatási szerződések sorai</span><span class="sxs-lookup"><span data-stu-id="42efb-126">Service-agreement lines</span></span>

<span data-ttu-id="42efb-127">A szolgáltatási szerződések minden egyes sora részletesen leírja a javasolt szervizmunka tartalmát.</span><span class="sxs-lookup"><span data-stu-id="42efb-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="42efb-128">A sorok a következő beállításokat tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="42efb-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="42efb-129">A tranzakció típusa és a tranzakciótípus leírása.</span><span class="sxs-lookup"><span data-stu-id="42efb-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="42efb-130">A szervizt végrehajtó alkalmazott nevét.</span><span class="sxs-lookup"><span data-stu-id="42efb-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="42efb-131">A tárgyat, amelyen a szolgáltatási szerződés szerint a szervizt végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="42efb-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="42efb-132">A gyakoriságot, amellyel a munkát végre kell hajtani, és a társított cikk-, költség- és díjtranzakciókat regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="42efb-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="42efb-133">Az időablakot, amelyen belül a szervizrendelés-sorok egy szervizrendelésbe csoportosíthatók.</span><span class="sxs-lookup"><span data-stu-id="42efb-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="42efb-134">Szerződéssorok csoportosítására használt szervizfeladatok, amelyek általános szinten összefoglalják a szerviztechnikusok és a vevők számára, hogy milyen szervizfeladatot kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="42efb-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="42efb-135">A sor le van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="42efb-135">Whether a line is stopped.</span></span> <span data-ttu-id="42efb-136">Ha egy sor le van állítva, akkor ahhoz nem hozható létre szervizrendelés.</span><span class="sxs-lookup"><span data-stu-id="42efb-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="42efb-137">Projektbeállítások, például a kategória és a sortulajdonság.</span><span class="sxs-lookup"><span data-stu-id="42efb-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42efb-138">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="42efb-138">Related topics</span></span>

[<span data-ttu-id="42efb-139">Szolgáltatási szerződések létrehozása</span><span class="sxs-lookup"><span data-stu-id="42efb-139">Create service agreements</span></span>](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]