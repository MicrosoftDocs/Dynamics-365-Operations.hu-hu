---
title: Modulkönyvtár – áttekintés
description: Ez a témakör a Microsoft Dynamics 365 Commerce modulkönyvtárról nyújt áttekintést.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dfc52dd8e14bb2e9f2f9c026ee0e058aee4cedcb
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817826"
---
# <a name="module-library-overview"></a><span data-ttu-id="92702-103">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="92702-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="92702-104">Ez a témakör a Microsoft Dynamics 365 Commerce modulkönyvtárról nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="92702-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

## <a name="overview"></a><span data-ttu-id="92702-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="92702-105">Overview</span></span>

<span data-ttu-id="92702-106">A Dynamics 365 Commerce modulkönyvtár olyan modulok gyűjteménye, amelyek egy e-kereskedelmi webhely felépítésére használhatók.</span><span class="sxs-lookup"><span data-stu-id="92702-106">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="92702-107">A modulokban felhasználói felületi (UI) szempontok és funkcionális működéssel kapcsolatos szempontok is találhatók.</span><span class="sxs-lookup"><span data-stu-id="92702-107">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="92702-108">A modulkönyvtár moduljaira témák is alkalmazhatók, így módosítható megjelenésük és hangulatuk.</span><span class="sxs-lookup"><span data-stu-id="92702-108">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="92702-109">A témák egymásra épülő stílusalapokat (CSS) használnak.</span><span class="sxs-lookup"><span data-stu-id="92702-109">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="92702-110">A „Gyár” nevű fiktív e-kereskedelmi webhely témája a elérhető a modulkönyvtár részeként, és referenciaként használható.</span><span class="sxs-lookup"><span data-stu-id="92702-110">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="92702-111">Modulkönyvtár moduljai</span><span class="sxs-lookup"><span data-stu-id="92702-111">Module library modules</span></span>

<span data-ttu-id="92702-112">A következő típusú modulok érhetők el a modellkönyvtárban:</span><span class="sxs-lookup"><span data-stu-id="92702-112">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="92702-113">**Konténer modul** – Egy konténer modul egy egyszerű modul, amely más modulok számára gazdaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="92702-113">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="92702-114">A benne található modulok elrendezését szabályozza.</span><span class="sxs-lookup"><span data-stu-id="92702-114">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="92702-115">**Marketing modulok** – A marketing modulokban megtalálhatók a blokk, a szövegblokk, a videólejátszó és a forgótár modulok.</span><span class="sxs-lookup"><span data-stu-id="92702-115">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="92702-116">Ezen a modulok mindegyike a tartalom bemutatására használható.</span><span class="sxs-lookup"><span data-stu-id="92702-116">All these modules can be used to showcase content.</span></span> <span data-ttu-id="92702-117">Ezeket a modulokat bármelyik lapra el lehet helyezni, és tartalomkezelő rendszer (CMS) adatai vezérlik őket.</span><span class="sxs-lookup"><span data-stu-id="92702-117">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="92702-118">**Fejléc és lábléc modulok** – A fejléc és lábléc modulok az oldal összes lapjának fej- és láblécében jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="92702-118">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="92702-119">Ezek a modulok a tulajdonságokon keresztül konfigurálhatók igény szerint.</span><span class="sxs-lookup"><span data-stu-id="92702-119">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="92702-120">**Keresési modulok** – A termékek a fejlécben található keresési modul segítségével fedezhetők fel.</span><span class="sxs-lookup"><span data-stu-id="92702-120">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="92702-121">A keresési eredmények a találati lapon jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="92702-121">Search results appear on the search results page.</span></span> <span data-ttu-id="92702-122">A termékek a kategória oldalain is megtalálhatók, amelyek különálló lapok az egyes kategóriákhoz, amelyek támogatva vannak a csatornanavigációban.</span><span class="sxs-lookup"><span data-stu-id="92702-122">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="92702-123">Ezenkívül a finomító modulok használhatók keresési eredmények és kategóriák oldalain található eredmények további szűrésére.</span><span class="sxs-lookup"><span data-stu-id="92702-123">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="92702-124">**A termék részletei lap moduljai** – A termék részletei oldalak számos modult használnak a termék adatainak megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="92702-124">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="92702-125">A vásárlásmező modul segítségével a vevők megtekintik a termékeket, és behelyezhetik őket a kosárba.</span><span class="sxs-lookup"><span data-stu-id="92702-125">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="92702-126">Más modulok – például a műszaki adatok modul – a termék részletes adatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="92702-126">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="92702-127">A minősítések és a vélemények modul a vélemények megjelenítésére és adására használható.</span><span class="sxs-lookup"><span data-stu-id="92702-127">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="92702-128">**Online vásárlás, felvétel az üzletben modul** – Az Online vásárlás, felvétel az üzletben modul integrálva van a Bing Maps-térképpel.</span><span class="sxs-lookup"><span data-stu-id="92702-128">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="92702-129">Felhasználható a közelben található üzletek megtalálására, ahol a vevők a megvásárolt termékeket átvehetik.</span><span class="sxs-lookup"><span data-stu-id="92702-129">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="92702-130">**Beszerzési modulok** – A beszerzési modulok tartalmazzák a kosár modult, amely a cikkek kosárba helyezésére használható.</span><span class="sxs-lookup"><span data-stu-id="92702-130">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="92702-131">A pénztári modul rögzíti a szállítási címet, a szállítási lehetőségeket és az ajándékutalvány, a hűségprogram- és a hitelkártya-adatokat, hogy fel lehessen dolgozni a rendelést.</span><span class="sxs-lookup"><span data-stu-id="92702-131">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="92702-132">A rendelés leadását követően a rendelés visszaigazolása modul a visszaigazolás részleteinek megjelenítésére is használható.</span><span class="sxs-lookup"><span data-stu-id="92702-132">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="92702-133">**Fiókkezelési modulok** – A bejelentkezési modulban a vevők be tudnak jelentkezni egy már létező fiókba, és a feliratkozási modul új fiók létrehozását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="92702-133">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="92702-134">A fiók létrehozása után a rendelési előzmények modulban megtekintheti a legutóbbi rendeléseket, és a rendelés részletei modulban megtekintheti a rendelés adatait.</span><span class="sxs-lookup"><span data-stu-id="92702-134">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="92702-135">**Javaslatok modul** – A javaslatok a termékmegjelenítés modul használatával jeleníthetők meg.</span><span class="sxs-lookup"><span data-stu-id="92702-135">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="92702-136">Ez a modul olyan algoritmus alapú és szerkesztői listákat támogat, amelyek bármelyik lapon megjeleníthetők.</span><span class="sxs-lookup"><span data-stu-id="92702-136">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92702-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="92702-137">Additional resources</span></span>

[<span data-ttu-id="92702-138">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="92702-138">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="92702-139">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="92702-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="92702-140">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="92702-140">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="92702-141">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="92702-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="92702-142">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="92702-142">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="92702-143">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="92702-143">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="92702-144">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="92702-144">Footer module</span></span>](author-footer-module.md)
