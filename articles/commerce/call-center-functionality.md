---
title: Hívásközpont eladási funkciói
description: Ez a témakör áttekintést ad a hívásközpont értékesítési funkcióiról a Dynamics 365 Commerce szolgáltatásban.
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
ms.openlocfilehash: 816bfc8b93f52fe91192874bcc1c8e605e41b582
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022747"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="c7c4d-103">Hívásközpont értékesítési funkciói</span><span class="sxs-lookup"><span data-stu-id="c7c4d-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="c7c4d-104">A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta csatorna, amelyet az alkalmazásban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-104">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="c7c4d-105">Ha meghatároznak egy adott csatornát a hívásközpont-entitásokhoz, az lehetővé teszi, hogy a hívásközponti csatorna felhasználója által létrehozott specifikus adatalapértelmezéseket és a rendelési alapértelmezéseket a rendszer értékesítési rendelésekhez kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="c7c4d-106">A hívásközpont funkciói speciális promóciókat tartalmaznak az árra vonatkozóan, valamint katalógusokat, ajándékutalványokat, hűségprogramokat és kuponokat.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-106">Call center features include advanced price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="c7c4d-107">A hívásközpont által lebonyolított rendeléseket segíti a pénztári (POS) alkalmazás, amely támogatja a párhuzamos csatornákon történő rendelések teljesítését.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="c7c4d-108">Fontos megjegyezni, hogy míg a hívásközpont-modul a kereskedelmi kívül más ágazatokban is használható, a telefonos ügyfélszolgálati alkalmazás jelenlegi kiadása még nem lett optimalizálva vállalatok közötti (B2B) rendelésfeldolgozási forgatókönyvekhez, illetve olyan forgatókönyvekhez, ahol a rendelésekhez nagy mennyiségű értékesítési sorok tartoznak.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-108">It's important to note that while the call center module can be utilized by other industries outside of Commerce, the current release of the call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="c7c4d-109">Azt ajánljuk, hogy azok a felhasználók, akik a hívásközpont funkcióit a szokásos, közvetlenül az ügyféllel lebonyolított műveleteken túlmenően akarják a megrendelések feldolgozására használni, szánjanak rá elegendő időt a telefonos ügyfélszolgálat tesztelésére és annak ellenőrzésére, hogy az teljesíti-e funkcionális és teljesítménybeli elvárásokat.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="c7c4d-110">A rendelések létrehozásának támogatásán felül a hívásközpont-modul felhasználóbarát ügyfélszolgálati alkalmazást is tartalmaz, amely megkönnyíti a felhasználók számára, hogy megkeressék a vevői számlákat és áttekintsék az összes kapcsolódó, vevői megrendeléshez kapcsolódó adatot és attribútumot.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="c7c4d-111">Az ügyfélszolgálati képernyő lehetővé teszi, hogy a felhasználó gyorsan elérje a rendeléshez kapcsolódó adatokat, amelyek lehetővé teszik, hogy gyorsan megválaszolja az ügyfelektől a rendelésekkel kapcsolatban kapott, leggyakoribb kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="c7c4d-112">Ez a lap a következőkhöz kapcsolódó dokumentációkhoz biztosít hivatkozásokat: beállítás, konfiguráció és a hívásközpont funkcióinak használata.</span><span class="sxs-lookup"><span data-stu-id="c7c4d-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="c7c4d-113">Hívásközpont konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-113">Configure the call center</span></span>

[<span data-ttu-id="c7c4d-114">Hívásközponti csatornák beállítása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="c7c4d-115">A megrendelés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-115">Configure order processing</span></span>

[<span data-ttu-id="c7c4d-116">Hívásközpontban jelentkező csalás-ellenőrzési figyelmeztetések beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="c7c4d-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="c7c4d-117">Hívásközpont rendeléseinek várakoztatása – konfigurálás és használat</span><span class="sxs-lookup"><span data-stu-id="c7c4d-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="c7c4d-118">Fizetés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-118">Configure payment processing</span></span>

[<span data-ttu-id="c7c4d-119">Fizetési módok hívásközpontoknál</span><span class="sxs-lookup"><span data-stu-id="c7c4d-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="c7c4d-120">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-120">Configure delivery modes</span></span>

[<span data-ttu-id="c7c4d-121">Szállítási módok és díjak beállítása a hívásközponthoz</span><span class="sxs-lookup"><span data-stu-id="c7c4d-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="c7c4d-122">Közvetlen marketing konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-122">Configure direct marketing</span></span>

[<span data-ttu-id="c7c4d-123">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="c7c4d-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="c7c4d-124">Frissesség, gyakoriság és pénzügyi szempont szerinti (Recency, Frequency, Monetary, RFM) elemzés beállítása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="c7c4d-125">Folytonossági programok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c7c4d-125">Configure continuity programs</span></span>

[<span data-ttu-id="c7c4d-126">Folytonossági programok beállítása hívásközpontok számára</span><span class="sxs-lookup"><span data-stu-id="c7c4d-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
