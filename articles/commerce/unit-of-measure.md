---
title: Mértékegység-beállítások alkalmazása
description: Ez a témakör a mértékegységek beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271401"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="8bfd3-103">Mértékegység-beállítások alkalmazása</span><span class="sxs-lookup"><span data-stu-id="8bfd3-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8bfd3-104">Ez a témakör a mértékegységek beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8bfd3-105">A termék különböző egységekben értékesíthető, például "darab", "pár" és "tucat".</span><span class="sxs-lookup"><span data-stu-id="8bfd3-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="8bfd3-106">A Commerce központban meg lehet adni egy termékhez az értékesítési egységét, és meg lehet jeleníteni egy e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="8bfd3-107">Ha például egy kiskereskedő külön-külön és tucatonként is értékesít egy terméket, a rendelkezésre álló mértékegységek más termékinformációkkal együtt megjeleníthetők.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="8bfd3-108">A következő példában a Commerce központban egy termékhez be van állítva egy **db** (darab) értékesítési egység.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Példa olyan termékre, amely a Commerce központban mértékegységgel van konfigurálva](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="8bfd3-110">A mértékegység alkalmazásának és megjelenítésének támogatása a Commerce rendszer 10.0.19-es verziójának kiadásától áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="8bfd3-111">Mértékegység-beállítások</span><span class="sxs-lookup"><span data-stu-id="8bfd3-111">Unit of measure settings</span></span>

<span data-ttu-id="8bfd3-112">A mértékegység-megjelenítési beállításokat a Commerce webhelyszerkesztőben, a **Webhelybeállítások \> Kiterjesztések \> Mértékegység-megjelenítés termékekhez** helyen lehet meghatározni.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="8bfd3-113">Három támogatott beállítás van:</span><span class="sxs-lookup"><span data-stu-id="8bfd3-113">There are three supported settings:</span></span>

- <span data-ttu-id="8bfd3-114">**Ne jelenítse meg** – Ha ez a beállítás ki van választva, akkor az e-commerce webhely nem mutatja meg a termék mértékegységét.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="8bfd3-115">Ez a viselkedés az alapértelmezett viselkedés.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="8bfd3-116">**Megjelenítés a termék vásárlási élményben** – Ha ez a beállítás be van jelölve, akkor a mértékegység megjelenik a termék részletei, a kosár, a pénztár, a rendelési előzmények és a rendelés részleteit tartalmazó lapokon.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="8bfd3-117">**Megjelenítés a termék böngészési és a vásárlási élményben** – Ha ez a beállítás van kiválasztva a mértékegység megjelenik a termékvásárlási élmény lapjain és a termékböngészési élményben is.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="8bfd3-118">A viselkedés részeként a mértékegységek megjelennek a keresési eredményekben és a termékgyűjtemény modulokban is.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bfd3-119">A mértékegység-megjelenítési beállítások a Commerce rendszer 10.0.19-es verziójú kiadásában érhetők el.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="8bfd3-120">Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="8bfd3-121">Az utasításokat lásd itt: [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="8bfd3-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="8bfd3-122">A mértékegység-beállításokat használó modulok</span><span class="sxs-lookup"><span data-stu-id="8bfd3-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="8bfd3-123">A mértékegység-beállításokat használó modulok közé tartozik a vásárlásmező, a kívánságlista, a kosár, a kosár ikon, a keresési eredmények tárolója, a termékgyűjtemény, a pénztár és a rendelés részletei modul.</span><span class="sxs-lookup"><span data-stu-id="8bfd3-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="8bfd3-124">A következő példában a termék részletező lapja (PDP) megjeleníti a termékhez tartozó mértékegységet (**db**).</span><span class="sxs-lookup"><span data-stu-id="8bfd3-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Példa a mértékegységet megjelenítő PDP-re](./media/Productunit-PDP.png)

<span data-ttu-id="8bfd3-126">A következő példában a termékgyűjtemény modul megjeleníti a termékhez tartozó mértékegységet (**db**).</span><span class="sxs-lookup"><span data-stu-id="8bfd3-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Példa a mértékegységet megjelenítő gyűjteménymodulra](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="8bfd3-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8bfd3-128">Additional resources</span></span>

[<span data-ttu-id="8bfd3-129">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="8bfd3-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8bfd3-130">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="8bfd3-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8bfd3-131">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="8bfd3-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8bfd3-132">Számlakezelési oldalak és modulok</span><span class="sxs-lookup"><span data-stu-id="8bfd3-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="8bfd3-133">SDK- és modultár-frissítések</span><span class="sxs-lookup"><span data-stu-id="8bfd3-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
