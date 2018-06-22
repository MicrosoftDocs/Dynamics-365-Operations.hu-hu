---
title: "Hívásközpont funkciói"
description: "A témakör a Microsoft Dynamics 365 for Retail hívásközpont-eladások funkcióit ismerteti."
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 6e4f89d86b64e0c8c76c15d3c2c1c00af353e9ca
ms.openlocfilehash: e76b29cf6312959ee84c251d582310ce4822945f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/17/2018

---

# <a name="call-center"></a><span data-ttu-id="9b1ce-103">Hívásközpont</span><span class="sxs-lookup"><span data-stu-id="9b1ce-103">Call center</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="9b1ce-104">A Dynamics 365 for Retail szolgáltatásban a hívásközpont egyfajta kiskereskedelmi csatorna, amelyet az alkalmazásban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-104">In Dynamics 365 for Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="9b1ce-105">Ha meghatároznak egy adott csatornát a hívásközpont-entitásokhoz, az lehetővé teszi, hogy a hívásközponti csatorna felhasználója által létrehozott specifikus adatalapértelmezéseket és a rendelési alapértelmezéseket a rendszer értékesítési rendelésekhez kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="9b1ce-106">A hívásközpont funkciói speciális promóciókat tartalmaznak a kiskereskedelmi árra vonatkozóan, valamint katalógusokat, ajándékutalványokat, hűségprogramokat és kuponokat.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="9b1ce-107">A hívásközpont által lebonyolított rendeléseket segíti a pénztári (POS) alkalmazás, amely támogatja a párhuzamos csatornákon történő rendelések teljesítését.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="9b1ce-108">Fontos megjegyezni, hogy míg a hívásközpont-modul a kiskereskedelmin kívül más ágazatokban is használható, a Dynamics 365 for Retail telefonos ügyfélszolgálati alkalmazás jelenlegi kiadása még nem lett optimalizálva vállalatok közötti (B2B) rendelésfeldolgozási forgatókönyvekhez, illetve olyan forgatókönyvekhez, ahol a rendelésekhez nagy mennyiségű értékesítési sorok tartoznak.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Dynamics 365 for Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="9b1ce-109">Azt ajánljuk, hogy azok a felhasználók, akik a hívásközpont funkcióit a szokásos, közvetlenül az ügyféllel lebonyolított műveleteken túlmenően akarják a megrendelések feldolgozására használni, szánjanak rá elegendő időt a telefonos ügyfélszolgálat tesztelésére és annak ellenőrzésére, hogy az teljesíti-e funkcionális és teljesítménybeli elvárásokat.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="9b1ce-110">A rendelések létrehozásának támogatásán felül a hívásközpont-modul felhasználóbarát ügyfélszolgálati alkalmazást is tartalmaz, amely megkönnyíti a felhasználók számára, hogy megkeressék a vevői számlákat és áttekintsék az összes kapcsolódó, vevői megrendeléshez kapcsolódó adatot és attribútumot.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="9b1ce-111">Az ügyfélszolgálati képernyő lehetővé teszi, hogy a felhasználó gyorsan elérje a rendeléshez kapcsolódó adatokat, amelyek lehetővé teszik, hogy gyorsan megválaszolja az ügyfelektől a rendelésekkel kapcsolatban kapott, leggyakoribb kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="9b1ce-112">Ez a lap a következőkhöz kapcsolódó dokumentációkhoz biztosít hivatkozásokat: beállítás, konfiguráció és a Dynamics 365 for Retail hívásközpont funkcióinak használata.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Dynamics 365 for Retail.</span></span>

## <a name="configure-the-call-center"></a><span data-ttu-id="9b1ce-113">Hívásközpont konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-113">Configure the call center</span></span>
[<span data-ttu-id="9b1ce-114">Rendelésfeldolgozási beállítások meghatározása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-114">Set up order processing options</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="9b1ce-115">A megrendelés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-115">Configure order processing</span></span>
[<span data-ttu-id="9b1ce-116">Csalással kapcsolatos figyelmeztetések beállítása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-116">Set up fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="9b1ce-117">Megrendelés manuális várakoztatása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-117">Manual Order Holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="9b1ce-118">Fizetés feldolgozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-118">Configure payment processing</span></span>
[<span data-ttu-id="9b1ce-119">Fizetési módszerek hívásközpontnál</span><span class="sxs-lookup"><span data-stu-id="9b1ce-119">Payment methods in a call center</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="9b1ce-120">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-120">Configure delivery modes</span></span>
[<span data-ttu-id="9b1ce-121">Szállítási módok és díjak beállítása a hívásközponthoz</span><span class="sxs-lookup"><span data-stu-id="9b1ce-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="9b1ce-122">Közvetlen marketing konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-122">Configure direct marketing</span></span>
[<span data-ttu-id="9b1ce-123">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="9b1ce-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="9b1ce-124">RFM-profilelemzés beállítása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-124">Set up RFM analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="9b1ce-125">Folytonossági programok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b1ce-125">Configure continuity programs</span></span>
[<span data-ttu-id="9b1ce-126">Folytonossági program beállítása egy hívásközpont számára</span><span class="sxs-lookup"><span data-stu-id="9b1ce-126">Set up a continuity program for a call center</span></span>](set-up-continuity-program.md)


