---
title: Hívásközpont eladási funkciói
description: Ez a témakör áttekintést ad a hívásközpont értékesítési funkcióiról a Dynamics 365 Retail szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2e44770af4a30f539e56d38b21c897cacd2707e7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812339"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="33a81-103">Hívásközpont értékesítési funkciói</span><span class="sxs-lookup"><span data-stu-id="33a81-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="33a81-104">A Dynamics 365 Retail szolgáltatásban a hívásközpont egyfajta kiskereskedelmi csatorna, amelyet az alkalmazásban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="33a81-104">In Dynamics 365 Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="33a81-105">Ha meghatároznak egy adott csatornát a hívásközpont-entitásokhoz, az lehetővé teszi, hogy a hívásközponti csatorna felhasználója által létrehozott specifikus adatalapértelmezéseket és a rendelési alapértelmezéseket a rendszer értékesítési rendelésekhez kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="33a81-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="33a81-106">A hívásközpont funkciói speciális promóciókat tartalmaznak a kiskereskedelmi árra vonatkozóan, valamint katalógusokat, ajándékutalványokat, hűségprogramokat és kuponokat.</span><span class="sxs-lookup"><span data-stu-id="33a81-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="33a81-107">A hívásközpont által lebonyolított rendeléseket segíti a pénztári (POS) alkalmazás, amely támogatja a párhuzamos csatornákon történő rendelések teljesítését.</span><span class="sxs-lookup"><span data-stu-id="33a81-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="33a81-108">Fontos megjegyezni, hogy míg a hívásközpont-modul a kiskereskedelmin kívül más ágazatokban is használható, a Retail telefonos ügyfélszolgálati alkalmazás jelenlegi kiadása még nem lett optimalizálva vállalatok közötti (B2B) rendelésfeldolgozási forgatókönyvekhez, illetve olyan forgatókönyvekhez, ahol a rendelésekhez nagy mennyiségű értékesítési sorok tartoznak.</span><span class="sxs-lookup"><span data-stu-id="33a81-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="33a81-109">Azt ajánljuk, hogy azok a felhasználók, akik a hívásközpont funkcióit a szokásos, közvetlenül az ügyféllel lebonyolított műveleteken túlmenően akarják a megrendelések feldolgozására használni, szánjanak rá elegendő időt a telefonos ügyfélszolgálat tesztelésére és annak ellenőrzésére, hogy az teljesíti-e funkcionális és teljesítménybeli elvárásokat.</span><span class="sxs-lookup"><span data-stu-id="33a81-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="33a81-110">A rendelések létrehozásának támogatásán felül a hívásközpont-modul felhasználóbarát ügyfélszolgálati alkalmazást is tartalmaz, amely megkönnyíti a felhasználók számára, hogy megkeressék a vevői számlákat és áttekintsék az összes kapcsolódó, vevői megrendeléshez kapcsolódó adatot és attribútumot.</span><span class="sxs-lookup"><span data-stu-id="33a81-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="33a81-111">Az ügyfélszolgálati képernyő lehetővé teszi, hogy a felhasználó gyorsan elérje a rendeléshez kapcsolódó adatokat, amelyek lehetővé teszik, hogy gyorsan megválaszolja az ügyfelektől a rendelésekkel kapcsolatban kapott, leggyakoribb kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="33a81-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="33a81-112">Ez a lap a következőkhöz kapcsolódó dokumentációkhoz biztosít hivatkozásokat: beállítás, konfiguráció és a Retail hívásközpont funkcióinak használata.</span><span class="sxs-lookup"><span data-stu-id="33a81-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Retail.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="33a81-113">Hívásközpont konfigurálása</span><span class="sxs-lookup"><span data-stu-id="33a81-113">Configure the call center</span></span>

[<span data-ttu-id="33a81-114">Hívásközponti csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="33a81-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="33a81-115">A megrendelés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="33a81-115">Configure order processing</span></span>

[<span data-ttu-id="33a81-116">Hívásközpontban jelentkező csalás-ellenőrzési figyelmeztetések beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="33a81-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="33a81-117">Hívásközpont rendeléseinek várakoztatása – konfigurálás és használat</span><span class="sxs-lookup"><span data-stu-id="33a81-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="33a81-118">Fizetés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="33a81-118">Configure payment processing</span></span>

[<span data-ttu-id="33a81-119">Fizetési módok hívásközpontoknál</span><span class="sxs-lookup"><span data-stu-id="33a81-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="33a81-120">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="33a81-120">Configure delivery modes</span></span>

[<span data-ttu-id="33a81-121">Szállítási módok és díjak beállítása a hívásközponthoz</span><span class="sxs-lookup"><span data-stu-id="33a81-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="33a81-122">Közvetlen marketing konfigurálása</span><span class="sxs-lookup"><span data-stu-id="33a81-122">Configure direct marketing</span></span>

[<span data-ttu-id="33a81-123">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="33a81-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="33a81-124">Frissesség, gyakoriság és pénzügyi szempont szerinti (Recency, Frequency, Monetary, RFM) elemzés beállítása</span><span class="sxs-lookup"><span data-stu-id="33a81-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="33a81-125">Folytonossági programok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="33a81-125">Configure continuity programs</span></span>

[<span data-ttu-id="33a81-126">Folytonossági programok beállítása hívásközpontok számára</span><span class="sxs-lookup"><span data-stu-id="33a81-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
