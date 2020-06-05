---
title: Üzletkiválasztó modul
description: Ez a témakör az üzletválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378208"
---
# <a name="store-selector-module"></a><span data-ttu-id="7f0bf-103">Üzletkiválasztó modul</span><span class="sxs-lookup"><span data-stu-id="7f0bf-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7f0bf-104">Ez a témakör az üzletválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7f0bf-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7f0bf-105">Overview</span></span>

<span data-ttu-id="7f0bf-106">Egy üzletválasztó modul van használatban az „online vásárlás, átvétel az áruházban” "(BOPIS) vevői forgatókönyvhöz.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="7f0bf-107">Megjeleníti azoknak az üzleteknek a listáját, amelyekben a termék rendelkezésre áll felvételre, valamint az egyes üzletekhez tartozó nyitva tartást és termékkészletet.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="7f0bf-108">Az üzletválasztó modulnak szükséges a termék kontextusa és egy keresési hely az üzletek megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="7f0bf-109">A keresési hely hiányában a vevő böngészőjének alapértelmezett helye lesz használva, ha a vevő ehhez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="7f0bf-110">A modulnak van egy beviteli doboza, amely lehetővé teszi, hogy a vevő megadjon egy helyet (irányítószámot vagy várost, illetve államot) a közelben található üzletek megtalálására.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="7f0bf-111">Az áruházválasztó modul integrálva van a Bing Maps földrajzi kódolási alkalmazásprogramozási felületével (API), hogy a vevő által megadott helyszínt egy földrajzi szélességgé és hosszúsággá alakíthassa.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="7f0bf-112">A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce megosztott paraméterei oldalhoz a Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7f0bf-113">Az üzletválasztó modul hozzáadható a termék részletei oldalon (PDP) található Vásárlásmező modulhoz, amelyben megtekinthetők azok az üzletek, amelyekben a termék rendelkezésre áll felvételre.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="7f0bf-114">A kosár modulhoz is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-114">It can also be added to a cart module.</span></span> <span data-ttu-id="7f0bf-115">A kosár modulhoz való felvételkor az üzletválasztó modul minden egyes kosár sortételhez megjeleníti az átvételi beállításokat.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="7f0bf-116">Ezenkívül az egyéni kódolással a modul hozzáadható más oldalakhoz vagy modulokhoz a bővítményeken és a testreszabásokon keresztül.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="7f0bf-117">A BOPIS szcenárió működéséhez a termékeket a „vevői átvétel” szállítási móddal kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="7f0bf-118">Máskülönben a modul nem fog megjelenni a megfelelő lapokon.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="7f0bf-119">A szállítási mód konfigurálásával kapcsolatos további tudnivalókat lásd: [Szállításimódok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="7f0bf-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="7f0bf-120">A következő kép a PDP-ben használt üzletválasztó modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Példa egy üzletválasztó modulra](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="7f0bf-122">Az Üzletválasztó modul használata az e-kereskedelemben</span><span class="sxs-lookup"><span data-stu-id="7f0bf-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="7f0bf-123">Az üzletválasztó modul hozzáadható a termék részletei oldalhoz (PDP) azon közeli üzletek megkereséséhez, amelyekben a termék rendelkezésre áll felvételre.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="7f0bf-124">Az üzletválasztó modul hozzáadható a kosároldalhoz azon közeli üzletek megkereséséhez, amelyekben a kosárban található termék rendelkezésre áll felvételre.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="7f0bf-125">Az üzletkiválasztó modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="7f0bf-125">Store selector module properties</span></span>

| <span data-ttu-id="7f0bf-126">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="7f0bf-126">Property name</span></span>             | <span data-ttu-id="7f0bf-127">Érték</span><span class="sxs-lookup"><span data-stu-id="7f0bf-127">Value</span></span>                 | <span data-ttu-id="7f0bf-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="7f0bf-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="7f0bf-129">Keresési sugár</span><span class="sxs-lookup"><span data-stu-id="7f0bf-129">Search radius</span></span> | <span data-ttu-id="7f0bf-130">Szám</span><span class="sxs-lookup"><span data-stu-id="7f0bf-130">Number</span></span> | <span data-ttu-id="7f0bf-131">Az üzletek keresési sugarát határozza meg (mérföldben).</span><span class="sxs-lookup"><span data-stu-id="7f0bf-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="7f0bf-132">Ha nincs megadva érték, akkor a program az alapértelmezett 50 mérföldes keresési sugarat használja.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="7f0bf-133">Szolgáltatási feltételek</span><span class="sxs-lookup"><span data-stu-id="7f0bf-133">Terms of Service</span></span> | <span data-ttu-id="7f0bf-134">URL-cím</span><span class="sxs-lookup"><span data-stu-id="7f0bf-134">URL</span></span>    |  <span data-ttu-id="7f0bf-135">A Bing Térképek szolgáltatáshoz a szolgáltatási feltételek hivatkozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="7f0bf-136">Üzletválasztó modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="7f0bf-136">Add a store selector module to a page</span></span>

<span data-ttu-id="7f0bf-137">Egy üzletválasztó modulnak szüksége van egy termék környezetére, így csak a vásárlásmező és a kosár modulokban használható.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="7f0bf-138">Az üzletválasztó modulok nem működnek ezeken a modulokon kívül.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="7f0bf-139">Az üzletválasztó modulnak egy vásárlásmező modulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Vásárlásmező](add-buy-box.md) modul.</span><span class="sxs-lookup"><span data-stu-id="7f0bf-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="7f0bf-140">Az üzletválasztó modulnak egy kosármodulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Kosár modul](add-cart-module.md).</span><span class="sxs-lookup"><span data-stu-id="7f0bf-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7f0bf-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7f0bf-141">Additional resources</span></span>

[<span data-ttu-id="7f0bf-142">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="7f0bf-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7f0bf-143">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="7f0bf-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="7f0bf-144">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="7f0bf-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7f0bf-145">A PDP rövid bemutatása</span><span class="sxs-lookup"><span data-stu-id="7f0bf-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="7f0bf-146">A kosár és a pénztár rövid bemutatása</span><span class="sxs-lookup"><span data-stu-id="7f0bf-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="7f0bf-147">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="7f0bf-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[<span data-ttu-id="7f0bf-148">A szervezethez tartozó Bing Térképek kezelése</span><span class="sxs-lookup"><span data-stu-id="7f0bf-148">Manage Bing Maps for your organization</span></span>](dev-itpro/manage-bing-maps.md)
