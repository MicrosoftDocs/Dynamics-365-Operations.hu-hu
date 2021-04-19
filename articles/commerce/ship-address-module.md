---
title: Szállítási cím modul
description: Ez a témakör ismerteti szállítási cím modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: fd48a04612159cbe29a2cc7cafea1c9c4c8745b4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795429"
---
# <a name="shipping-address-module"></a><span data-ttu-id="8f162-103">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="8f162-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f162-104">Ez a témakör ismerteti szállítási cím modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8f162-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8f162-105">A szállítási cím modul segítségével a vásárlók hozzáadhatnak vagy kiválaszthatnak egy szállítási címet egy rendeléshez a fizetési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="8f162-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="8f162-106">Ha egy vásárló be van jelentkezve, minden addig mentett cím megjelenítésre kerül a vásárlónak, és a vásárló akár közülük is választhat.</span><span class="sxs-lookup"><span data-stu-id="8f162-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="8f162-107">A vevő új címet is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="8f162-107">The customer can also add a new address.</span></span> <span data-ttu-id="8f162-108">A szállítási cím modul minden cikkre használható, amely szállítást igényel.</span><span class="sxs-lookup"><span data-stu-id="8f162-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="8f162-109">A szállítási cím formátumok megadhatók a Commerce headquartersben minden országra vagy régióra, és a szállítási cím modul ezután ország/régió specifikus szabályokat érvényesít.</span><span class="sxs-lookup"><span data-stu-id="8f162-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="8f162-110">Amikor egy vevő megad egy szállítási címet a fizetési folyamatban, lehetőségük van elmenteni a címet elsődleges címként.</span><span class="sxs-lookup"><span data-stu-id="8f162-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="8f162-111">Ez a lehetőség csak a bejelentkezett vevők számára jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="8f162-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="8f162-112">Bár a szállítási cím modul nem biztosít címellenőrzést, ez a funkció implementálható a modul testreszabása által.</span><span class="sxs-lookup"><span data-stu-id="8f162-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="8f162-113">A következő illusztráció egy példát ábrázol egy új szállítási cím modulra egy fizetési oldalon.</span><span class="sxs-lookup"><span data-stu-id="8f162-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Példa egy szállítási cím modulra egy fizetési oldalon](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="8f162-115">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="8f162-115">Module properties</span></span>

| <span data-ttu-id="8f162-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="8f162-116">Property name</span></span> | <span data-ttu-id="8f162-117">Értékek</span><span class="sxs-lookup"><span data-stu-id="8f162-117">Values</span></span> | <span data-ttu-id="8f162-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="8f162-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="8f162-119">Fejléc</span><span class="sxs-lookup"><span data-stu-id="8f162-119">Heading</span></span> | <span data-ttu-id="8f162-120">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="8f162-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="8f162-121">A szállítási cím modul választható címsora.</span><span class="sxs-lookup"><span data-stu-id="8f162-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="8f162-122">Címtípus megjelenítése</span><span class="sxs-lookup"><span data-stu-id="8f162-122">Show address type</span></span> | <span data-ttu-id="8f162-123">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="8f162-123">**True** or **False**</span></span> | <span data-ttu-id="8f162-124">Ha ez a választható tulajdonság **Igaz** értékre van állítva, akkor egy címtípus vetődik fel, mint például az **Otthon** vagy az **Üzleti** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="8f162-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="8f162-125">Ha nincs megadva címtípus, a cím automatikusan mentésre kerül **Típus**=**Egyéb** címkével.</span><span class="sxs-lookup"><span data-stu-id="8f162-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="8f162-126">Automatikus javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="8f162-126">Enable auto suggestion</span></span>| <span data-ttu-id="8f162-127">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="8f162-127">**True** or **False**</span></span> | <span data-ttu-id="8f162-128">Ha ez az opcionális tulajdonság **Igaz**, a rendszer automatikus címjavaslatokat ad.</span><span class="sxs-lookup"><span data-stu-id="8f162-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="8f162-129">Ezeket a javaslatokat a Bing Térképek biztosítja.</span><span class="sxs-lookup"><span data-stu-id="8f162-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="8f162-130">A webhely Bing Térképek-integrációjának beállítására vonatkozó tudnivalókat lásd: [Üzletválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="8f162-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="8f162-131">Ez a funkció már elérhető a Commerce alkalmazás 10.0.15-ös kiadásában.</span><span class="sxs-lookup"><span data-stu-id="8f162-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="8f162-132">Automatikus javaslat beállításai</span><span class="sxs-lookup"><span data-stu-id="8f162-132">Auto suggest options</span></span>| <span data-ttu-id="8f162-133">Egy szám</span><span class="sxs-lookup"><span data-stu-id="8f162-133">A number</span></span>| <span data-ttu-id="8f162-134">Ha engedélyezve vannak az automatikus címjavaslatok, megadhatja a további beállításokat is, például a nyújtható javaslatok maximális számát.</span><span class="sxs-lookup"><span data-stu-id="8f162-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="8f162-135">Adjon hozzá egy szállítási cím modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat</span><span class="sxs-lookup"><span data-stu-id="8f162-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="8f162-136">A szállítási cím modul csak a pénztár modulhoz adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="8f162-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="8f162-137">A szállítási cím konfigurálásával és fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkért lásd: [Fizetési modul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="8f162-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f162-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8f162-138">Additional resources</span></span>

[<span data-ttu-id="8f162-139">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="8f162-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8f162-140">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="8f162-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="8f162-141">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="8f162-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8f162-142">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="8f162-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="8f162-143">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="8f162-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="8f162-144">Átvételi információ modul</span><span class="sxs-lookup"><span data-stu-id="8f162-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="8f162-145">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="8f162-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8f162-146">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="8f162-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="8f162-147">Üzletválasztó modul</span><span class="sxs-lookup"><span data-stu-id="8f162-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]