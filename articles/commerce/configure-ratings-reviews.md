---
title: Minősítések és értékelések konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770481"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="5f3b8-103">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-103">Configure ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5f3b8-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5f3b8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5f3b8-105">Overview</span></span>

<span data-ttu-id="5f3b8-106">Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, és megmutatják, hogy egyéb vevők mit gondolnak ezekről a termékekről.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="5f3b8-107">Az e-kereskedelmi webhelyek esetében a minősítések és értékelések a termékekkel kapcsolatos vevői visszajelzések összegyűjtésének mechanizmusai is egyben.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="5f3b8-108">Az értékelések a termék listaoldalakon, kategória listaoldalakon, a keresési találatok oldalain és a webhely más oldalain jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="5f3b8-109">Az értékelési hisztogramok és a termékértékelések a termék részletes lapjain (PDP-k) jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="5f3b8-110">A **Vélemény írása** gombra kattintva a vevők elküldhetik a termékkel kapcsolatos értékeléseket és véleményeket.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="5f3b8-111">Értékelések és vélemények modulok a PDP-ken</span><span class="sxs-lookup"><span data-stu-id="5f3b8-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="5f3b8-112">Három modul mutatja az értékelések és vélemények összesítését a PDP-ken:</span><span class="sxs-lookup"><span data-stu-id="5f3b8-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="5f3b8-113">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-113">Write review module</span></span>
- <span data-ttu-id="5f3b8-114">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-114">Product reviews list module</span></span>
- <span data-ttu-id="5f3b8-115">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-115">Ratings histogram module</span></span>
 
<span data-ttu-id="5f3b8-116">A következő ábra bemutatja, hogyan jelennek meg az értékelések és vélemények modulok egy PDP-n.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Értékelések és vélemények modulok a PDP-ken](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="5f3b8-118">Ha további tájékoztatást szeretne kapni a PDP-sablonok és -elrendezések optimalizálásával kapcsolatban, hogy az e-kereskedelmi webhelyének több PDP-je között megoszthassa az értékelések és vélemények modulok konfigurációit, tekintse meg a következőt: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5f3b8-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="5f3b8-119">A következő ábra bemutatja, hogyan mutatja be a **Modul hozzáadása** párbeszédpanel az értékelések és vélemények modulokat a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Modul hozzáadása párbeszédpanel](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="5f3b8-121">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-121">Write review module</span></span>

<span data-ttu-id="5f3b8-122">A vélemény írása modul egy **Vélemény írása** gombot tartalmaz, amely lehetővé teszi a felhasználók számára a bejelentkezést, egy értékelés hozzárendelését és a termékkel kapcsolatos vélemény megírását.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="5f3b8-123">Ez a modul azt is lehetővé teszi, hogy a felhasználók szerkesszék a korábban elküldött értékelést vagy véleményt.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="5f3b8-124">Ez a modul általában az értékelési hisztogram és a termékvélemények listájának moduljai fölött jelenik meg a PDP-ben.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="5f3b8-125">A következő ábra bemutatja, hogyan jeleníti meg a **Vélemény írása** párbeszédpanel, amikor a vevő a **Vélemény írása** lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="5f3b8-126">A vevő ezt a párbeszédpanelt használhatja az értékelés és vélemény elküldésére.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Vélemény írása párbeszédpanel](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="5f3b8-128">A következő táblázat bemutatja a vélemény írása modul tulajdonságot, amelyet a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="5f3b8-129">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="5f3b8-129">Property name</span></span> | <span data-ttu-id="5f3b8-130">Érték</span><span class="sxs-lookup"><span data-stu-id="5f3b8-130">Value</span></span>        | <span data-ttu-id="5f3b8-131">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="5f3b8-132">Név</span><span class="sxs-lookup"><span data-stu-id="5f3b8-132">Name</span></span>          | <span data-ttu-id="5f3b8-133">Vélemény írása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-133">Write review</span></span> | <span data-ttu-id="5f3b8-134">A vélemény írása modul neve.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="5f3b8-135">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-135">Ratings histogram module</span></span>

<span data-ttu-id="5f3b8-136">Az értékelési hisztogram modul az értékelések hisztogramját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="5f3b8-137">Ez a modul általában a vélemény írása modul és a termékvélemények listája modul között jelenik meg a PDP-n.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="5f3b8-138">Az értékelési hisztogram modul nem igényel konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="5f3b8-139">Csak fel kell vennie a modult a PDP-sablonba.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="5f3b8-140">A következő illusztrációk azt mutatják, hogy milyen egy PDP-sablon a Dynamics 365 Commerce alkalmazásban, amikor az értékelések és vélemények modulok a PDP-ken való megjelenítésre vannak konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![PDP-sablon, ha az értékelések és vélemények a PDP-n történő megjelenítésre vannak konfigurálva.](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="5f3b8-142">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="5f3b8-142">Product reviews list module</span></span>

<span data-ttu-id="5f3b8-143">A termékvélemények listája modul felsorolja a termékkel kapcsolatos véleményeket rendezési, szűrési és tördelési beállításokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="5f3b8-144">Ez a modul a PDP-n általában egy értékelési hisztogram modul után jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="5f3b8-145">A következő táblázat bemutatja a termékvélemények listája modul tulajdonságokat, amelyeket a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="5f3b8-146">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="5f3b8-146">Property name</span></span>              | <span data-ttu-id="5f3b8-147">Érték</span><span class="sxs-lookup"><span data-stu-id="5f3b8-147">Value</span></span> | <span data-ttu-id="5f3b8-148">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="5f3b8-149">Az egyes oldalakon megjelenített vélemények</span><span class="sxs-lookup"><span data-stu-id="5f3b8-149">Reviews shown on each page</span></span> | <span data-ttu-id="5f3b8-150">10</span><span class="sxs-lookup"><span data-stu-id="5f3b8-150">10</span></span>    | <span data-ttu-id="5f3b8-151">Egy PDP-n egyidejűleg megjelenített vélemények száma.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="5f3b8-152">A **Következő** és **Előző** gomb segítségével a felhasználók a véleményeket tartalmazó lapok között navigálhatnak.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="5f3b8-153">Értékelési hisztogram – Összesítő nézet</span><span class="sxs-lookup"><span data-stu-id="5f3b8-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="5f3b8-154">A termékvélemények listája modul tartalmaz egy olyan helyet, ahol hozzáadhat egy értékelési hisztogram modult.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="5f3b8-155">A következő ábra azt mutatja be, hogyan lehet az értékelési hisztogram modult hozzáadni a termékvélemények listája modulhoz a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Értékelési hisztogram modul hozzáadása egy termékvélemények listája modulhoz](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="5f3b8-157">A webhely konfigurálása értékelések és vélemények megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="5f3b8-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="5f3b8-158">Az értékelések és vélemények értékeinek konfigurációs értékei, például a bérlőazonosító, a vélemény szövegének hossza és a vélemény címének hossza, a webhely szintjén konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="5f3b8-159">Tegye a következőket a webhely konfigurálásához az értékelések és vélemények megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="5f3b8-160">Lépjen a **Kezdőlap \> Webhelyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="5f3b8-161">Válassza ki a webhely nevét.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="5f3b8-162">Lépjen a **Webhely kezelése \> Bővíthetőség** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="5f3b8-163">A **Vélemény szövegének maximális hossza** mezőbe írja be, hogy a vélemények szövege legfeljebb hány karakterből állhat (például **1000**).</span><span class="sxs-lookup"><span data-stu-id="5f3b8-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="5f3b8-164">A **Vélemény címének maximális hossza** mezőbe írja be, hogy a vélemények címei legfeljebb hány karakterből állhatnak (például **55**).</span><span class="sxs-lookup"><span data-stu-id="5f3b8-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="5f3b8-165">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="5f3b8-166">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Webhely konfigurálása értékelések és vélemények megjelenítésére](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="5f3b8-168">Termékértékelés hivatkozása egy PDP Vélemények szakaszához.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="5f3b8-169">A termékértékelés a termék címe alatt jelenik meg a PDP felső részén.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="5f3b8-170">A termékértékelés konfigurálható úgy, hogy az ugyanannak a PDP-nek az **Vélemények** szakaszához legyen társítva.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="5f3b8-171">Egy termékértékelésnek a PDP **Vélemények** szakaszához való társításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="5f3b8-172">Nyissa meg a PDP-sablont.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="5f3b8-173">Lépjen a **Vásárlásmező tárolómoduljának beállításai** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="5f3b8-174">A **Vásárlásmező** alatt válassza ki a **Termékértékelések** elemet, majd válassza a **Kattintás hivatkozása a teljes vélemények modulhoz** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="5f3b8-175">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Termékértékelés hivatkozása egy PDP Vélemények szakaszához](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="5f3b8-177">Az adatvédelem és irányelvek lap hivatkozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="5f3b8-178">Az adatvédelem és irányelvek lap hivatkozásának konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="5f3b8-179">Lépjen a **Kezdőlap \> Webhelyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="5f3b8-180">Válassza ki a webhely nevét.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="5f3b8-181">Lépjen a **Webhely kezelése \> Bővíthetőség** lehetőségre</span><span class="sxs-lookup"><span data-stu-id="5f3b8-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="5f3b8-182">Az **Útvonalak** lapon az **RNR adatvédelem és irányelvek** alatt válassza a **Hivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="5f3b8-183">Ha már meg van adva egy hivatkozás, és ki szeretné cserélni, válassza ki a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="5f3b8-184">A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az adatvédelem és irányelvek lap hivatkozását, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="5f3b8-185">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="5f3b8-186">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5f3b8-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Az adatvédelem és irányelvek lap hivatkozásának konfigurálása](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="5f3b8-188">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5f3b8-188">Additional resources</span></span>

[<span data-ttu-id="5f3b8-189">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="5f3b8-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="5f3b8-190">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="5f3b8-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="5f3b8-191">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="5f3b8-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="5f3b8-192">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="5f3b8-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
