---
title: Termékadatok oldalainak áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékrészletek oldalairól (PDP-k).
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
ms.openlocfilehash: c53e74204fad2960dfba972a38c511df7d6672d8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412967"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="8a31e-103">Termékadatok oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a31e-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8a31e-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékrészletek oldalairól (PDP-k).</span><span class="sxs-lookup"><span data-stu-id="8a31e-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8a31e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="8a31e-105">Overview</span></span>

<span data-ttu-id="8a31e-106">A PDP részletes információt nyújt a termékről, és a vevők számára lehetővé teszi a termékopciók például a méret, a stílus és a szín kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="8a31e-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="8a31e-107">A PDP-nek meg kell jelenítenie az összes olyan termékre vonatkozó információt, amely a vevőnek a beszerzési döntés meghozatalához szükséges.</span><span class="sxs-lookup"><span data-stu-id="8a31e-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="8a31e-108">A következő ábrán a PDP egy példája látható.</span><span class="sxs-lookup"><span data-stu-id="8a31e-108">The following illustration shows an example of a PDP.</span></span>

![Példa a termék részleteit tartalmazó oldalra](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="8a31e-110">Fejléc- és láblécmodulok</span><span class="sxs-lookup"><span data-stu-id="8a31e-110">Header and footer modules</span></span>

<span data-ttu-id="8a31e-111">A PDP felső részén egy fejléc jelenik meg, amely az összes termékkategóriát és az egyéb olyan oldalakt, amelyet a kereskedő azt szeretné, hogy böngésznének.</span><span class="sxs-lookup"><span data-stu-id="8a31e-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="8a31e-112">A lap alján van egy lábléc, amely gyorshivatkozásokat tartalmaz a különböző témájú témákhoz, amelyek érdekesek lehetnek a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="8a31e-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="8a31e-113">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="8a31e-113">Buy box module</span></span>

<span data-ttu-id="8a31e-114">A PDP legfontosabb modulja a vásárlásmező modul, amely a lap fő szakaszának első elemeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="8a31e-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="8a31e-115">A Vásárlásmező modul fontos termék adatait jeleníti meg, mint például a termék neve, a termék leírása, a termék ára, a termék képei és a termék minősítései.</span><span class="sxs-lookup"><span data-stu-id="8a31e-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="8a31e-116">A vásárlódoboz modul lehetővé teszi a vevő számára a termék opciók kiválasztását (például a méretet, a stílust és a színt), illetve azt, hogy a terméket hozzáadja a kosárhoz.</span><span class="sxs-lookup"><span data-stu-id="8a31e-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="8a31e-117">Azt is lehetővé teszi, hogy a vevő online vásárolja meg a terméket, és vegye egy üzletben vegye át.</span><span class="sxs-lookup"><span data-stu-id="8a31e-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="8a31e-118">A vásárlás online és az átvétel üzletben modul a Bing Maps alkalmazásprogramozási felületek (API-k) integrációját használja hogy megkeresse a közeli üzleteket vagy üzleteket egy másiik helye, amit az ügyfél meghatároz.</span><span class="sxs-lookup"><span data-stu-id="8a31e-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="8a31e-119">A vásárlódoboz modulhoz termékazonosító szükséges.</span><span class="sxs-lookup"><span data-stu-id="8a31e-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="8a31e-120">Ez az azonosító az oldal kontextusából van származtatva.</span><span class="sxs-lookup"><span data-stu-id="8a31e-120">This ID is derived from the page context.</span></span> <span data-ttu-id="8a31e-121">Ha egy vásárlómező modult egy olyan oldalhoz ad hozzá, amelyben a lap környezete nem tartalmaz termékazonosítót, akkor az az adatokat nem fogja helyesen megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="8a31e-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="8a31e-122">Termékleírások modul</span><span class="sxs-lookup"><span data-stu-id="8a31e-122">Product specifications module</span></span>

<span data-ttu-id="8a31e-123">A termékleírások modul a termékkel kapcsolatos további részletek megjelenítésére használható.</span><span class="sxs-lookup"><span data-stu-id="8a31e-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="8a31e-124">Ezek a részletek a termékattribútumokból származnak a Commerce alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="8a31e-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="8a31e-125">A termékspecifikációk modulja minden olyan attribútumot megjelenít, amelyben a **látható** tulajdonság **igaz** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="8a31e-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="8a31e-126">A termékattribútumok beolvasásához szükséges a termékazonosító.</span><span class="sxs-lookup"><span data-stu-id="8a31e-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="8a31e-127">Ajánlatok modul</span><span class="sxs-lookup"><span data-stu-id="8a31e-127">Recommendations module</span></span>

<span data-ttu-id="8a31e-128">A PDP egyik fontos modulja az ajánlatok modul.</span><span class="sxs-lookup"><span data-stu-id="8a31e-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="8a31e-129">Miközben a vevők böngészik a termékeket, további termék lehetőségeket kell megjeleníteni számukra, hogy megtalálják a megfelelő terméket, és megvásárolhassák azt.</span><span class="sxs-lookup"><span data-stu-id="8a31e-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="8a31e-130">Ajánlások segítik a vevőket, hogy könnyen felfedezhessék a kapcsolódó tartalmakat, és folytathassák a vásárlást.</span><span class="sxs-lookup"><span data-stu-id="8a31e-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="8a31e-131">Különböző típusú ajánláslisták érhetők el:</span><span class="sxs-lookup"><span data-stu-id="8a31e-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="8a31e-132">Az **Emberek ezt is szeretik** lista gépi tanuláson alapul.</span><span class="sxs-lookup"><span data-stu-id="8a31e-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="8a31e-133">A többi vevő tranzakciós előzményeit használja a javaslatok biztosítására.</span><span class="sxs-lookup"><span data-stu-id="8a31e-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="8a31e-134">Ezt a listát a javaslatok szolgáltatás hozza létre, és a „Vásárlók akik megvásárolták a következőket is megvásárolták…” listákhoz hasonlít.</span><span class="sxs-lookup"><span data-stu-id="8a31e-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="8a31e-135">A lista létrehozásához egy termékazonosító szükséges.</span><span class="sxs-lookup"><span data-stu-id="8a31e-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="8a31e-136">A Commerce termékeihez konfigurálható egy **Kapcsolódó** lista.</span><span class="sxs-lookup"><span data-stu-id="8a31e-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="8a31e-137">Például egy barna bőr utazás kézitáskához, több bőr kézitáska, iletve más utzaásokhoz készült tásaki is konfigurálható a kapcsolódó listához.</span><span class="sxs-lookup"><span data-stu-id="8a31e-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="8a31e-138">Más típusú kapcsolódó listák, például a **Tartozékok** és **Több ehhez hasonló** is konfigurálható a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8a31e-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="8a31e-139">A lista létrehozásához egy termékazonosító szükséges.</span><span class="sxs-lookup"><span data-stu-id="8a31e-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="8a31e-140">Ha tehát egy kezdőlaphoz adják hozzá, és a lap környezete nem tartalmaz termékazonosítót, akkor a lista üres lesz.</span><span class="sxs-lookup"><span data-stu-id="8a31e-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="8a31e-141">Algoritmus alapján léterhozott ajánlási listák listák, például **Népszerű**, **Legnépszerűbb** és **Új** használhatók a PDP-ken.</span><span class="sxs-lookup"><span data-stu-id="8a31e-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="8a31e-142">Annak ellenére, hogy ezek a listák nem közvetlenül kapcsolódnak a PDP termékeihez, egy másik módot kínálnak arra, hogy a vevők könnyebben megtalálják azokat a termékeket, amelyek érdekesek lehetnek számukra.</span><span class="sxs-lookup"><span data-stu-id="8a31e-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="8a31e-143">Az ilyen típusú listákhoz nem szükséges termékazonosító.</span><span class="sxs-lookup"><span data-stu-id="8a31e-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="8a31e-144">Ezek általános listák, amelyek a webhelyen tapasztalható különböző vásárlási szokások alapján jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="8a31e-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="8a31e-145">A Szerkesztői listák manuálisan válogatott listák.</span><span class="sxs-lookup"><span data-stu-id="8a31e-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="8a31e-146">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy manuálisan szeretné összeállítani a bemutatni kívánt termékek listáját.</span><span class="sxs-lookup"><span data-stu-id="8a31e-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="8a31e-147">Értékelések és vélemények modulok</span><span class="sxs-lookup"><span data-stu-id="8a31e-147">Ratings and reviews modules</span></span>

<span data-ttu-id="8a31e-148">Három modul használható a vélemények megjelenítésére és hozzáadására:</span><span class="sxs-lookup"><span data-stu-id="8a31e-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="8a31e-149">**Értékelések** – ez a modul a más vevők által adott értékeléseket és véleményeket listázza.</span><span class="sxs-lookup"><span data-stu-id="8a31e-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="8a31e-150">A vevők rendezni és szűrni tudják a véleményeket.</span><span class="sxs-lookup"><span data-stu-id="8a31e-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="8a31e-151">Ez a modul a vevők kedvelt vagy nem kedvelt értékelését, valamint a problémák jelentését is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="8a31e-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="8a31e-152">**Értékelés írása** – ezzel a modullal a vevők saját értékelést írhatnak a termékhez.</span><span class="sxs-lookup"><span data-stu-id="8a31e-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="8a31e-153">**Minősítési hisztogram**  – ez a modul tartalmaz egy olyan hisztogramot, amely egy termék minősítési tendenciáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="8a31e-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="8a31e-154">További részletekért lásd: [Minősítések és értékelések áttekintése](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a31e-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="8a31e-155">Marketing modulok</span><span class="sxs-lookup"><span data-stu-id="8a31e-155">Marketing modules</span></span>

<span data-ttu-id="8a31e-156">Ha egy adott termék esetében a marketingtartalom egyedi, akkor a PDP-hez bármilyen marketingmodul hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="8a31e-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="8a31e-157">A marketingmodulokat egy PDP-hez a lap „gazdaggá tétele” révén lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="8a31e-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="8a31e-158">A további tudnivalókat lásd [A termékoldal bővítése](enrich-product-page.md) lapon.</span><span class="sxs-lookup"><span data-stu-id="8a31e-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a31e-159">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8a31e-159">Additional resources</span></span>

[<span data-ttu-id="8a31e-160">Kezdőlap áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a31e-160">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="8a31e-161">Kosár és pénztár oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a31e-161">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="8a31e-162">Fiókkezelési oldalak áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a31e-162">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="8a31e-163">A termékoldal bővítése lap</span><span class="sxs-lookup"><span data-stu-id="8a31e-163">Enrich a product details page</span></span>](enrich-product-page.md)
