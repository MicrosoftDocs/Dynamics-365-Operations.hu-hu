---
title: Szállítási lehetőségek modul
description: Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 04/23/2021
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
ms.openlocfilehash: 12b0281a27dcf5f567bcd6be5530fa8e26a4ae99
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937482"
---
# <a name="delivery-options-module"></a><span data-ttu-id="f3d58-103">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f3d58-104">Ez a témakör ismerteti a szállítási lehetőségek modult, és bemutatja, hogyan konfigurálhatjuk őket a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f3d58-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f3d58-105">A szállítási lehetőségek modulok lehetővé teszik a vevők számára, hogy kiválaszthassanak egy szállítási módot, mint például a szállítást vagy a felvételt online rendeléseikhez.</span><span class="sxs-lookup"><span data-stu-id="f3d58-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="f3d58-106">A szállítási mód megadásához szállítási cím szükséges.</span><span class="sxs-lookup"><span data-stu-id="f3d58-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="f3d58-107">Ha a szállítási cím megváltozik, a szállítási lehetőségek újra lekérésre kell kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="f3d58-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="f3d58-108">Ha a rendelés csak olyan cikkeket tartalmaz, melyek az üzletben átvehető, ez a modul automatikusan elrejtésre kerül.</span><span class="sxs-lookup"><span data-stu-id="f3d58-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="f3d58-109">A szállítási módok konfigurálásával kapcsolatos tudnivalókért lásd: [Online csatorna-beállítások](channel-setup-online.md) és a [Szállítási módok beállításai](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="f3d58-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="f3d58-110">Minden szállítási módhoz kapcsolódó költség is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="f3d58-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="f3d58-111">Az online áruházakhoz tartozó költségek konfigurálásával kapcsolatos bővebb tájékoztatásért lásd: [Többcsatornás speciális automatikus költségek](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="f3d58-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="f3d58-112">A Commerce 10.0.13-es verziójában a szállítási lehetőségek modul frissítése megtörtént, így az támogatja a **Fejlécköltségek  arányosítás nélkül** és a **Sorköltségként történő szállítás** funkciókat.</span><span class="sxs-lookup"><span data-stu-id="f3d58-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="f3d58-113">Ha az arányosítás ki van kapcsolva, a várakozás szerint az e-Commerce munkafolyamat nem fogja engedélyezni a vegyes módú szállítást a cikkekre a kosárban (ez azt jelenti, hogy néhány cikk szállításra lesz kiválasztva, néhány pedig felvételre).</span><span class="sxs-lookup"><span data-stu-id="f3d58-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="f3d58-114">A **Fejlécköltségek arányosítás nélkül** funkcióhoz szükséges a **Konzisztens szállítási mód kezelésének engedélyezése a csatornában** jelölő be kell legyen kapcsolva a Commerce headquartersben.</span><span class="sxs-lookup"><span data-stu-id="f3d58-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag is turned on in Commerce headquarters.</span></span> <span data-ttu-id="f3d58-115">Ha a funkció jelölő be van kapcsolva, szállítási díjak kapcsolódhatnak mind a fejléc szinten, mind a sor szinten, függően a Commerce headquarters beállításaitól.</span><span class="sxs-lookup"><span data-stu-id="f3d58-115">When the feature flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="f3d58-116">A Fabrikam téma támogatja a kevert módú szállítást, ahol egyes cikkek szállításra vannak kiválasztva, a másikak pedig felvételre.</span><span class="sxs-lookup"><span data-stu-id="f3d58-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="f3d58-117">Ebben a módban a szállítási költségek arányosításra kerülnek minden cikkre, amelyek a kiszállítás szállítási móddal kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="f3d58-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="f3d58-118">A vegyes szállítási mód működéséhez először konfigurálnia kell a **Fejlécköltségek arányosítással** funkciót a Commerce headquartersben.</span><span class="sxs-lookup"><span data-stu-id="f3d58-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="f3d58-119">A konfigurációval kapcsolatos további információkét lásd: [Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="f3d58-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="f3d58-120">Ha egy sortételhez szállítási költségek tartoznak, azok megjelenítésre kerülnek a kosár sorban cikkenként.</span><span class="sxs-lookup"><span data-stu-id="f3d58-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="f3d58-121">Ez a funkció megköveteli, hogy a **Szállítási költségek megjelenítése a sortételeken** lehetőség be legyen kapcsolva mind a kosármodulon, mind a fizetési modulon.</span><span class="sxs-lookup"><span data-stu-id="f3d58-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="f3d58-122">A további tudnivalókért lásd: [Kosármodul](add-cart-module.md)és [Fizetési modul ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="f3d58-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="f3d58-123">A következő ábra bemutat egy példát egy szállítási lehetőségek modulról egy fizetési oldalon.</span><span class="sxs-lookup"><span data-stu-id="f3d58-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Példa egy szállítási lehetőségek modulra egy fizetési oldalon](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="f3d58-125">Szállítási lehetőségek modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="f3d58-125">Delivery options module properties</span></span>

| <span data-ttu-id="f3d58-126">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="f3d58-126">Property</span></span> | <span data-ttu-id="f3d58-127">Értékek</span><span class="sxs-lookup"><span data-stu-id="f3d58-127">Values</span></span> | <span data-ttu-id="f3d58-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="f3d58-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="f3d58-129">Fejléc</span><span class="sxs-lookup"><span data-stu-id="f3d58-129">Heading</span></span> | <span data-ttu-id="f3d58-130">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="f3d58-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="f3d58-131">A szállítási lehetőségek modul választható címsora.</span><span class="sxs-lookup"><span data-stu-id="f3d58-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="f3d58-132">Egyéni CSS-osztály neve</span><span class="sxs-lookup"><span data-stu-id="f3d58-132">Custom CSS class name</span></span> | <span data-ttu-id="f3d58-133">Szöveg</span><span class="sxs-lookup"><span data-stu-id="f3d58-133">Text</span></span> | <span data-ttu-id="f3d58-134">Egy testreszabott Cascading Style Sheets (CSS) osztály neve, arra használatos, hogy mutassa ezt a modult, ha alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="f3d58-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="f3d58-135">Szállítási mód beállítás szűrése</span><span class="sxs-lookup"><span data-stu-id="f3d58-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="f3d58-136">**Szűrés mellőzése** vagy **Nem-szállítási módok**</span><span class="sxs-lookup"><span data-stu-id="f3d58-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="f3d58-137">Egy értéknek, amely meghatározza a szállítási lehetőségek modult, ki kell szűrnie minden nem-szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="f3d58-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |
| <span data-ttu-id="f3d58-138">Szállítási beállítás automatikus kiválasztása</span><span class="sxs-lookup"><span data-stu-id="f3d58-138">Auto select a delivery option</span></span> | <span data-ttu-id="f3d58-139">**Ne szűrje**, **Szállítási beállítás automatikus kiválasztása és összegzés mutatása**, vagy **Szállítási beállítás automatikus kiválasztása és összegzés elrejtése**</span><span class="sxs-lookup"><span data-stu-id="f3d58-139">**Do not filter**, **Auto select delivery option and show summary**, or **Auto select delivery option and don't show summary**</span></span> | <span data-ttu-id="f3d58-140">Ez a tulajdonság automatikusan alkalmazza az elsőként rendelkezésre álló szállítási lehetőséget a pénztárnál anélkül, hogy a felhasználónak ki kell választania.</span><span class="sxs-lookup"><span data-stu-id="f3d58-140">This property automatically applies the first available delivery option to checkout without requiring the user to select it.</span></span> <span data-ttu-id="f3d58-141">Csak akkor használja, ha van egy elérhető szállítási lehetőség.</span><span class="sxs-lookup"><span data-stu-id="f3d58-141">It should be used only if there is one available delivery option.</span></span> <span data-ttu-id="f3d58-142">Ez a tulajdonság támogatott a Commerce alkalmazás 10.0.19-ös kiadástól.</span><span class="sxs-lookup"><span data-stu-id="f3d58-142">This property is supported as of the Commerce version 10.0.19 release.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="f3d58-143">Adjon hozzá egy szállítási lehetőségek modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat</span><span class="sxs-lookup"><span data-stu-id="f3d58-143">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="f3d58-144">A szállítási lehetőségek modul csak a pénztár modulhoz adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="f3d58-144">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="f3d58-145">A szállítási lehetőségek modul konfigurálásával és a fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkét lásd: [Fizetési modul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="f3d58-145">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3d58-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f3d58-146">Additional resources</span></span>

[<span data-ttu-id="f3d58-147">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="f3d58-147">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f3d58-148">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="f3d58-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f3d58-149">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="f3d58-150">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="f3d58-151">Átvételi információk modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-151">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="f3d58-152">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-152">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f3d58-153">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="f3d58-153">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="f3d58-154">Online csatorna-beállítások</span><span class="sxs-lookup"><span data-stu-id="f3d58-154">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="f3d58-155">Többcsatornás speciális automatikus költségek</span><span class="sxs-lookup"><span data-stu-id="f3d58-155">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="f3d58-156">Fejlécköltségek arányosítása az egyező értékesítési sorokhoz</span><span class="sxs-lookup"><span data-stu-id="f3d58-156">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="f3d58-157">Szállítási módok beállítása</span><span class="sxs-lookup"><span data-stu-id="f3d58-157">Set up modes of delivery</span></span>](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
