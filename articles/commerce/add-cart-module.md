---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025436"
---
# <a name="cart-module"></a><span data-ttu-id="35472-103">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="35472-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="35472-104">Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="35472-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="35472-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="35472-105">Overview</span></span>

<span data-ttu-id="35472-106">A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép.</span><span class="sxs-lookup"><span data-stu-id="35472-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="35472-107">Tartalmazza például az összes kosárhoz adott elemet és a rendelés összesítését.</span><span class="sxs-lookup"><span data-stu-id="35472-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="35472-108">Lehetővé teszi, hogy az ügyfél promóciós kódokat alkalmazzon vagy távolítson el.</span><span class="sxs-lookup"><span data-stu-id="35472-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="35472-109">A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést.</span><span class="sxs-lookup"><span data-stu-id="35472-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="35472-110">Támogatja a **Vissza a vásárláshoz** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="35472-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="35472-111">A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.</span><span class="sxs-lookup"><span data-stu-id="35472-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="35472-112">A kosármodul a kosár azonosítója alapján jeleníti meg az adatokat.</span><span class="sxs-lookup"><span data-stu-id="35472-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="35472-113">A kosár azonosítója a webhely egészén elérhető böngésző-cookie.</span><span class="sxs-lookup"><span data-stu-id="35472-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="35472-114">A kosármodul tulajdonságai és helyei</span><span class="sxs-lookup"><span data-stu-id="35472-114">Cart module properties and slots</span></span>

<span data-ttu-id="35472-115">A kosár modulnak van egy **Címsor** tulajdonsága, amelyet olyan értékekre állíthat, mint **Bevásárlótáska** vagy **Kosárban levő cikkek**.</span><span class="sxs-lookup"><span data-stu-id="35472-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="35472-116">A kosármodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="35472-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="35472-117">**Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja.</span><span class="sxs-lookup"><span data-stu-id="35472-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="35472-118">Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.</span><span class="sxs-lookup"><span data-stu-id="35472-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="35472-119">Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.</span><span class="sxs-lookup"><span data-stu-id="35472-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="35472-120">**Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők.</span><span class="sxs-lookup"><span data-stu-id="35472-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="35472-121">Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják.</span><span class="sxs-lookup"><span data-stu-id="35472-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="35472-122">Az áruházválasztó modul integrálva van a Bing Maps földrajzi kódolási alkalmazásprogramozási felületével (API), hogy a vevő által megadott helyszínt egy földrajzi szélességgé és hosszúsággá alakíthassa.</span><span class="sxs-lookup"><span data-stu-id="35472-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="35472-123">A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Retail megosztott paraméterei oldalhoz a Dynamics 365 Retail szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="35472-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="35472-124">Ez a modul két tulajdonságot támogat, **Keresési sugár** és **Szolgáltatási feltételek hivatkozását**.</span><span class="sxs-lookup"><span data-stu-id="35472-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="35472-125">A **Keresési sugár** tulajdonság az üzletek keresési sugarát határozza meg (mérföldben).</span><span class="sxs-lookup"><span data-stu-id="35472-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="35472-126">Ha nincs megadva érték, akkor a program az alapértelmezett keresési sugarat (50 mérföld) használja.</span><span class="sxs-lookup"><span data-stu-id="35472-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="35472-127">Ha Bing-térképeket vagy külső szolgáltatásokat használnak, a **szolgáltatási feltételek hivatkozása** tulajdonsággal lehet hivatkozást biztosítani a szolgáltatási feltételekhez.</span><span class="sxs-lookup"><span data-stu-id="35472-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="35472-128">A Bing Maps szolgáltatáshoz a szolgáltatási feltételek hivatkozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="35472-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="35472-129">Kosármodul beállításai</span><span class="sxs-lookup"><span data-stu-id="35472-129">Cart module settings</span></span>

<span data-ttu-id="35472-130">A kosár-modulok beállításai a **Webhelybeállítások \> Bővítmények** pontban konfigurálhatók:</span><span class="sxs-lookup"><span data-stu-id="35472-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="35472-131">**Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát.</span><span class="sxs-lookup"><span data-stu-id="35472-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="35472-132">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.</span><span class="sxs-lookup"><span data-stu-id="35472-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="35472-133">**Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van.</span><span class="sxs-lookup"><span data-stu-id="35472-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="35472-134">Ez a készletellenőrzés végrehajtásra kerül mind azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel.</span><span class="sxs-lookup"><span data-stu-id="35472-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="35472-135">Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül.</span><span class="sxs-lookup"><span data-stu-id="35472-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="35472-136">**Készletpuffer** – ez a tulajdonság a készlethez tartozó pufferméret meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="35472-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="35472-137">A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása.</span><span class="sxs-lookup"><span data-stu-id="35472-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="35472-138">A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli.</span><span class="sxs-lookup"><span data-stu-id="35472-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="35472-139">Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="35472-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="35472-140">**Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="35472-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="35472-141">Ez az útvonal a webhely szintjén konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="35472-141">This route can be configured at the site level.</span></span> <span data-ttu-id="35472-142">Ennek a konfigurációnak köszönhetően a kiskereskedők visszavihetik a vevőt a webhely kezdőlapjára vagy más lapjára.</span><span class="sxs-lookup"><span data-stu-id="35472-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="35472-143">Commerce Scale Unit-interakció</span><span class="sxs-lookup"><span data-stu-id="35472-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="35472-144">A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be.</span><span class="sxs-lookup"><span data-stu-id="35472-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="35472-145">A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.</span><span class="sxs-lookup"><span data-stu-id="35472-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="35472-146">Kosármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="35472-146">Add a cart module to a page</span></span>

<span data-ttu-id="35472-147">A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35472-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="35472-148">Hozzon létre egy **Kosártöredék** nevű töredéket, majd adjon hozzá egy kosármodult.</span><span class="sxs-lookup"><span data-stu-id="35472-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="35472-149">Adjon hozzá egy fejlécet a kosármodulhoz.</span><span class="sxs-lookup"><span data-stu-id="35472-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="35472-150">Adjon hozzá egy üzletválasztó modult a kosár modulhoz.</span><span class="sxs-lookup"><span data-stu-id="35472-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="35472-151">Mentse a töredéket, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="35472-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="35472-152">Hozzon létre egy **Kosársablon** nevű sablont, és adja hozzá a most létrehozott kosártöredéket.</span><span class="sxs-lookup"><span data-stu-id="35472-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="35472-153">Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="35472-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="35472-154">Hozzon létre egy olyan oldalt, amely az új sablont használja.</span><span class="sxs-lookup"><span data-stu-id="35472-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="35472-155">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="35472-155">Save and preview the page.</span></span>
1. <span data-ttu-id="35472-156">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="35472-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35472-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="35472-157">Additional resources</span></span>

[<span data-ttu-id="35472-158">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="35472-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="35472-159">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="35472-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="35472-160">Vásárlásmező modul</span><span class="sxs-lookup"><span data-stu-id="35472-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="35472-161">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="35472-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="35472-162">Rendelésmegerősítés modul</span><span class="sxs-lookup"><span data-stu-id="35472-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="35472-163">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="35472-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="35472-164">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="35472-164">Footer module</span></span>](author-footer-module.md)
