---
title: Szállítási cím modul
description: Ez a témakör ismerteti szállítási cím modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: aeaa410fde29b285fdbbdd6acac19b0c4e917aa5
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2020
ms.locfileid: "4413023"
---
# <a name="shipping-address-module"></a><span data-ttu-id="bac01-103">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="bac01-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bac01-104">Ez a témakor ismerteti a szállítási cím modult, és bemutatja, hogyan kell konfigurálni azt a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="bac01-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bac01-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="bac01-105">Overview</span></span>

<span data-ttu-id="bac01-106">A szállítási cím modul segítségével a vásárlók hozzáadhatnak vagy kiválaszthatnak egy szállítási címet egy rendeléshez a fizetési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="bac01-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="bac01-107">Ha egy vásárló be van jelentkezve, minden addig mentett cím megjelenítésre kerül a vásárlónak, és a vásárló akár közülük is választhat.</span><span class="sxs-lookup"><span data-stu-id="bac01-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="bac01-108">A vevő új címet is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="bac01-108">The customer can also add a new address.</span></span> <span data-ttu-id="bac01-109">A szállítási cím modul minden cikkre használható, amely szállítást igényel.</span><span class="sxs-lookup"><span data-stu-id="bac01-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="bac01-110">A szállítási cím formátumok megadhatók a Commerce headquartersben minden országra vagy régióra, és a szállítási cím modul ezután ország/régió specifikus szabályokat érvényesít.</span><span class="sxs-lookup"><span data-stu-id="bac01-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="bac01-111">Amikor egy vevő megad egy szállítási címet a fizetési folyamatban, lehetőségük van elmenteni a címet elsődleges címként.</span><span class="sxs-lookup"><span data-stu-id="bac01-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="bac01-112">Ez a lehetőség csak a bejelentkezett vevők számára jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="bac01-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="bac01-113">Bár a szállítási cím modul nem biztosít címellenőrzést, ez a funkció implementálható a modul testreszabása által.</span><span class="sxs-lookup"><span data-stu-id="bac01-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="bac01-114">A következő illusztráció egy példát ábrázol egy új szállítási cím modulra egy fizetési oldalon.</span><span class="sxs-lookup"><span data-stu-id="bac01-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Példa egy szállítási cím modulra egy fizetési oldalon](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="bac01-116">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="bac01-116">Module properties</span></span>

| <span data-ttu-id="bac01-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="bac01-117">Property name</span></span> | <span data-ttu-id="bac01-118">Értékek</span><span class="sxs-lookup"><span data-stu-id="bac01-118">Values</span></span> | <span data-ttu-id="bac01-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="bac01-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="bac01-120">Fejléc</span><span class="sxs-lookup"><span data-stu-id="bac01-120">Heading</span></span> | <span data-ttu-id="bac01-121">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="bac01-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="bac01-122">A szállítási cím modul választható címsora.</span><span class="sxs-lookup"><span data-stu-id="bac01-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="bac01-123">Címtípus megjelenítése</span><span class="sxs-lookup"><span data-stu-id="bac01-123">Show address type</span></span> | <span data-ttu-id="bac01-124">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="bac01-124">**True** or **False**</span></span> | <span data-ttu-id="bac01-125">Ha ez a választható tulajdonság **Igaz** értékre van állítva, akkor egy címtípus vetődik fel, mint például az **Otthon** vagy az **Üzleti** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="bac01-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="bac01-126">Ha nincs megadva címtípus, a cím automatikusan mentésre kerül **Típus**=**Egyéb** címkével.</span><span class="sxs-lookup"><span data-stu-id="bac01-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="bac01-127">Adjon hozzá egy szállítási cím modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat</span><span class="sxs-lookup"><span data-stu-id="bac01-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="bac01-128">A szállítási cím modul csak a pénztár modulhoz adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="bac01-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="bac01-129">A szállítási cím konfigurálásával és fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkért lásd: [Fizetési modul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="bac01-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bac01-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bac01-130">Additional resources</span></span>

[<span data-ttu-id="bac01-131">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="bac01-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="bac01-132">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="bac01-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="bac01-133">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="bac01-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="bac01-134">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="bac01-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="bac01-135">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="bac01-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="bac01-136">Átvételi információk modul</span><span class="sxs-lookup"><span data-stu-id="bac01-136">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="bac01-137">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="bac01-137">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="bac01-138">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="bac01-138">Gift card module</span></span>](add-giftcard.md)
