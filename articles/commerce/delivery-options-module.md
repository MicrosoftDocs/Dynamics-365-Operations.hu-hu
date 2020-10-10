---
title: Szállítási lehetőségek modul
description: Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 39e597b88afcca69623b1a23acc95e4da3873082
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818299"
---
# <a name="delivery-options-module"></a><span data-ttu-id="5b0d2-103">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b0d2-104">Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5b0d2-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5b0d2-105">Overview</span></span>

<span data-ttu-id="5b0d2-106">A szállítási lehetőségek modulok lehetővé teszik a vevők számára, hogy kiválaszthassanak egy szállítási módot, mint például a szállítást vagy a felvételt online rendeléseikhez.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-106">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="5b0d2-107">A szállítási mód megadásához szállítási cím szükséges.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-107">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="5b0d2-108">Ha a szállítási cím megváltozik, a szállítási lehetőségek újra lekérésre kell kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-108">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="5b0d2-109">Ha a rendelés csak olyan cikkeket tartalmaz, melyek az üzletben átvehető, ez a modul automatikusan elrejtésre kerül.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-109">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="5b0d2-110">A szállítási módok konfigurálásával kapcsolatos tudnivalókért lásd: [Online csatorna-beállítások](channel-setup-online.md) és a [Szállítási módok beállításai](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-110">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="5b0d2-111">Minden szállítási módhoz kapcsolódó költség is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-111">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="5b0d2-112">Az online áruházakhoz tartozó költségek konfigurálásával kapcsolatos bővebb tájékoztatásért lásd: [Többcsatornás speciális automatikus költségek](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-112">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="5b0d2-113">A Commerce 10.0.13-es verziójában a szállítási lehetőségek modul frissítése megtörtént, így az támogatja a **Fejlécköltségek  arányosítás nélkül** és a **Sorköltségként történő szállítás** funkciókat.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-113">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="5b0d2-114">Ha az arányosítás ki van kapcsolva, a várakozás szerint az e-Commerce munkafolyamat nem fogja engedélyezni a vegyes módú szállítást a cikkekre a kosárban (ez azt jelenti, hogy néhány cikk szállításra lesz kiválasztva, néhány pedig felvételre).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-114">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="5b0d2-115">A **Fejlécköltségek arányosítás nélkül** funkcióhoz szükséges a **Konzisztens szállítási mód kezelésének engedélyezése a csatornában** jelölő be kell legyen kapcsolva a Commerce headquartersben.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-115">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="5b0d2-116">Ha a jelölő be van kapcsolva, szállítási díjak kapcsolódhatnak mind a fejléc szinten, mind a sor szinten, függően a Commerce headquarters beállításaitól.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-116">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="5b0d2-117">A Fabrikam téma támogatja a kevert módú szállítást, ahol egyes cikkek szállításra vannak kiválasztva, a másikak pedig felvételre.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-117">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="5b0d2-118">Ebben a módban a szállítási költségek arányosításra kerülnek minden cikkre, amelyek a kiszállítás szállítási móddal kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-118">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="5b0d2-119">A vegyes szállítási mód működéséhez először konfigurálnia kell a **Fejlécköltségek arányosítással** funkciót a Commerce headquartersben.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-119">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="5b0d2-120">A konfigurációval kapcsolatos további információkét lásd: [Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-120">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="5b0d2-121">Ha egy sortételhez szállítási költségek tartoznak, azok megjelenítésre kerülnek a kosár sorban cikkenként.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-121">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="5b0d2-122">Ez a funkció megköveteli, hogy a **Szállítási költségek megjelenítése a sortételeken** lehetőség be legyen kapcsolva mind a kosármodulon, mind a fizetési modulon.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-122">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="5b0d2-123">A további tudnivalókért lásd: [Kosármodul](add-cart-module.md)és [Fizetési modul ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-123">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="5b0d2-124">A következő ábra bemutat egy példát egy szállítási lehetőségek modulról egy fizetési oldalon.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-124">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Példa egy szállítási lehetőségek modulra egy fizetési oldalon](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="5b0d2-126">Szállítási lehetőségek modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="5b0d2-126">Delivery options module properties</span></span>

| <span data-ttu-id="5b0d2-127">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="5b0d2-127">Property</span></span> | <span data-ttu-id="5b0d2-128">Értékek</span><span class="sxs-lookup"><span data-stu-id="5b0d2-128">Values</span></span> | <span data-ttu-id="5b0d2-129">Leírás</span><span class="sxs-lookup"><span data-stu-id="5b0d2-129">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="5b0d2-130">Fejléc</span><span class="sxs-lookup"><span data-stu-id="5b0d2-130">Heading</span></span> | <span data-ttu-id="5b0d2-131">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="5b0d2-131">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="5b0d2-132">A szállítási lehetőségek modul választható címsora.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-132">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="5b0d2-133">Egyéni CSS-osztály neve</span><span class="sxs-lookup"><span data-stu-id="5b0d2-133">Custom CSS class name</span></span> | <span data-ttu-id="5b0d2-134">Szöveg</span><span class="sxs-lookup"><span data-stu-id="5b0d2-134">Text</span></span> | <span data-ttu-id="5b0d2-135">Egy testreszabott Cascading Style Sheets (CSS) osztály neve, arra használatos, hogy mutassa ezt a modult, ha alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-135">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="5b0d2-136">Szállítási mód beállítás szűrése</span><span class="sxs-lookup"><span data-stu-id="5b0d2-136">Filter Delivery Mode Option</span></span> | <span data-ttu-id="5b0d2-137">**Szűrés mellőzése** vagy **Nem-szállítási módok**</span><span class="sxs-lookup"><span data-stu-id="5b0d2-137">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="5b0d2-138">Egy értéknek, amely meghatározza a szállítási lehetőségek modult, ki kell szűrnie minden nem-szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-138">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="5b0d2-139">Adjon hozzá egy szállítási lehetőségek modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat</span><span class="sxs-lookup"><span data-stu-id="5b0d2-139">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="5b0d2-140">A szállítási lehetőségek modul csak a pénztár modulhoz adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="5b0d2-140">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="5b0d2-141">A szállítási lehetőségek modul konfigurálásával és a fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkét lásd: [Fizetési modul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d2-141">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b0d2-142">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5b0d2-142">Additional resources</span></span>

[<span data-ttu-id="5b0d2-143">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-143">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5b0d2-144">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5b0d2-145">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5b0d2-146">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5b0d2-147">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5b0d2-148">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="5b0d2-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="5b0d2-149">Online csatorna-beállítások</span><span class="sxs-lookup"><span data-stu-id="5b0d2-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="5b0d2-150">Többcsatornás speciális automatikus költségek</span><span class="sxs-lookup"><span data-stu-id="5b0d2-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="5b0d2-151">Fejlécköltségek arányosítása az egyező értékesítési sorokhoz</span><span class="sxs-lookup"><span data-stu-id="5b0d2-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="5b0d2-152">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="5b0d2-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
