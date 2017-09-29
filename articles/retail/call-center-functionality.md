---
title: "Hívásközpont funkciói"
description: "A cikk a Microsoft Dynamics 365 for Retail hívásközpont-eladások funkcióit ismerteti."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 00d24e9933d087f150ec5270da94ad911423824d
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="call-center-functionality"></a><span data-ttu-id="d8f7b-103">Hívásközpont funkciói</span><span class="sxs-lookup"><span data-stu-id="d8f7b-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d8f7b-104">A cikk a Microsoft Dynamics 365 for Retail hívásközpont-eladások funkcióit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="d8f7b-105">A Dynamics 365 for Retail rendszer támogatja a hívásközpontokat is mint kiskereskedelmi csatorna típust.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="d8f7b-106">A hívásközpontban a dolgozók telefonon vesznek fel rendeléseket a vevőktől, és értékesítési rendeléseket hoznak léte.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="d8f7b-107">A hívásközpont-funkció olyan szolgáltatásokat kínál, amelyekkel könnyebben felvehetők a telefonos rendelések és a vevőszolgálat kezelése a rendelés teljesítésének folyamatában.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="d8f7b-108">Például a hívásközpont munkatársai közvetlenül az értékesítési rendelésben adhatják meg a fizetési információkat, és megtekinthetik a költségek és kifizetések részletes összefoglalóját a rendelés leadása előtt.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="d8f7b-109">A dolgozók szabályozzák az árképzést is, és az **Értékesítési rendelés** oldalról számos adathoz hozzá tudnak férni a vevőkkel, termékekkel és árakkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="d8f7b-110">Mindemellett a hívásközponti továbbfejlesztett funkciókat kínál a vevői előzmények és a rendelés állapotának nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="d8f7b-111">Minden egyes hívásközpont lehet a saját felhasználói, fizetési módok, árcsoportok, pénzügyi dimenziók és szállítási módok.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="d8f7b-112">Beállítható, hogy ezek a beállítások a hívásközpont létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="d8f7b-113">Emellett a **Hívásközpont** oldal használatával engedélyezheti vagy letilthatja a következő, csak hívásközpontokra jellemző funkciócsoportokat:</span><span class="sxs-lookup"><span data-stu-id="d8f7b-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="d8f7b-114">**Rendelés teljesítése**– Ebbe a csoportba tartoznak a fizetéshez és a rendelés teljesítéséhez kötődő funkciók az **Értékesítési rendelés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="d8f7b-115">**Irányított eladás** – Ebbe a csoportba tartoznak a forráskódokhoz, parancsfájlokhoz és a katalógus kérelmekhez kötődő funkciók.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="d8f7b-116">Miután engedélyezte ezeket a funkciókat a hívásközpont beállításainál, elérhetővé válnak az **Értékesítési rendelés** oldalon azon felhasználók számára, akiket a hívásközponthoz társítottak.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="d8f7b-117">A legtöbb szolgáltatás szükséges további beállítási, használat előtt.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="d8f7b-118">Mielőtt a felhasználók létrehozhatnának hívásközpontos rendeléseket, hozzá kell adnia ezeket a felhasználókat a hívásközponthoz felhasználóként.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="d8f7b-119">Ez a lépés engedélyezi a hívásközpont csatornaspecifikus konfigurációját és funkcióit.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="d8f7b-120">Következzék pár példa az elérhetővé váló funkciókra:</span><span class="sxs-lookup"><span data-stu-id="d8f7b-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="d8f7b-121">Az irányított értékesítés telemarketinges szövegkönyvek és termékképek konfigurációs lehetőségeit kínálja, amelyek segíthetik és irányíthatják az értékesítőt a rendelés felvétele során.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-121">Guided selling provides configuration options for telesales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="d8f7b-122">A rendelés nem teljesíthető, amíg az értékesítő nem rögzített legalább egy fizetési módszert.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="d8f7b-123">A fel- és keresztértékesítési szabályok is konfigurálhatók, hogy bizonyos termékek népszerűsítésére bíztassák az értékesítőt.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="d8f7b-124">Az értékesítő rögzítheti az ügyfél által a rendeléshez használt katalógus forráskódját.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="d8f7b-125">Az értékesítő kiskereskedői kupont adhat hozzá a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="d8f7b-126">Az értékesítő folytonossági programokat is értékesíthet.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="d8f7b-127">A rendeléseket kézileg vagy automatikusan is várakoztathatja, hogy jelezze, ha további vizsgálat szükséges a rendelés feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="d8f7b-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





