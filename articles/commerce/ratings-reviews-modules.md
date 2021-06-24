---
title: Értékelések és vélemények modulok
description: Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain használt minősítési és az értékelési modulokat tárgyalja.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: a243399536fec3f5361104289c38e550bf8b1144
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193282"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="fe8a9-103">Minősítések és értékelések modulok</span><span class="sxs-lookup"><span data-stu-id="fe8a9-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe8a9-104">Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain (PDP-k) használt minősítési és az értékelési modulokat tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="fe8a9-105">Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, ugyanakkor egy módszert jelentenek a termékkel kapcsolatos ügyfél-visszajelzések gyűjtésére.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-105">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="fe8a9-106">Az értékelések a termék listaoldalakon, kategória listaoldalakon, a keresési találatok oldalain és a webhely más oldalain jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-106">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="fe8a9-107">Az értékelési hisztogramok és a termékértékelések a PDP-ken jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-107">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="fe8a9-108">A **Vélemény írása** gombra kattintva a vevők elküldhetik a termékkel kapcsolatos értékeléseket és véleményeket.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-108">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="fe8a9-109">Ezeket a PDP-funkciókat a minősítési és a felülvizsgálati modulok vezérlik.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-109">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="fe8a9-110">Értékelések és vélemények modulok a PDP-ken</span><span class="sxs-lookup"><span data-stu-id="fe8a9-110">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="fe8a9-111">Három modul mutatja az értékelések és vélemények összesítését a PDP-ken:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-111">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="fe8a9-112">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-112">Write review module</span></span>
- <span data-ttu-id="fe8a9-113">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-113">Product reviews list module</span></span>
- <span data-ttu-id="fe8a9-114">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-114">Ratings histogram module</span></span>
 
<span data-ttu-id="fe8a9-115">A következő ábra bemutatja, hogyan jelennek meg az értékelések és vélemények modulok egy PDP-n.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-115">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Értékelések és vélemények modulok a PDP-ken](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="fe8a9-117">Ha további tájékoztatást szeretne kapni a PDP-sablonok és -elrendezések optimalizálásával kapcsolatban, hogy az e-kereskedelmi webhelyének több PDP-je között megoszthassa az értékelések és vélemények modulok konfigurációit, tekintse meg a következőt: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe8a9-117">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="fe8a9-118">A következő ábra bemutatja, hogyan mutatja be a **Modul hozzáadása** párbeszédpanel az értékelések és vélemények modulokat a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-118">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="fe8a9-119">![Modul hozzáadása párbeszédpanel](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="fe8a9-119">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="fe8a9-120">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-120">Write review module</span></span>

<span data-ttu-id="fe8a9-121">A vélemény írása modul egy **Vélemény írása** gombot tartalmaz, amely lehetővé teszi a felhasználók számára a bejelentkezést, egy értékelés hozzárendelését és a termékkel kapcsolatos vélemény megírását.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-121">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="fe8a9-122">Ez a modul azt is lehetővé teszi, hogy a felhasználók szerkesszék a korábban elküldött értékelést vagy véleményt.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-122">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="fe8a9-123">Ez a modul általában az értékelési hisztogram és a termékvélemények listájának moduljai fölött jelenik meg a PDP-ben.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-123">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="fe8a9-124">A következő ábra bemutatja, hogyan jeleníti meg a **Vélemény írása** párbeszédpanel, amikor a vevő a **Vélemény írása** lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-124">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="fe8a9-125">A vevő ezt a párbeszédpanelt használhatja az értékelés és vélemény elküldésére.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-125">The customer can use this dialog box to submit a rating and a review.</span></span>

![Vélemény írása párbeszédpanel](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="fe8a9-127">A következő táblázat bemutatja a vélemény írása modul tulajdonságot, amelyet a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-127">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="fe8a9-128">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="fe8a9-128">Property name</span></span> | <span data-ttu-id="fe8a9-129">Érték</span><span class="sxs-lookup"><span data-stu-id="fe8a9-129">Value</span></span>        | <span data-ttu-id="fe8a9-130">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="fe8a9-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="fe8a9-131">Név</span><span class="sxs-lookup"><span data-stu-id="fe8a9-131">Name</span></span>          | <span data-ttu-id="fe8a9-132">Vélemény írása</span><span class="sxs-lookup"><span data-stu-id="fe8a9-132">Write review</span></span> | <span data-ttu-id="fe8a9-133">A vélemény írása modul neve.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="fe8a9-134">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-134">Ratings histogram module</span></span>

<span data-ttu-id="fe8a9-135">Az értékelési hisztogram modul az értékelések hisztogramját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="fe8a9-136">Ez a modul általában a vélemény írása modul és a termékvélemények listája modul között jelenik meg a PDP-n.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="fe8a9-137">Az értékelési hisztogram modul nem igényel konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="fe8a9-138">Csak fel kell vennie a modult a PDP-sablonba.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="fe8a9-139">A következő illusztrációk azt mutatják, hogy milyen egy PDP-sablon a Dynamics 365 Commerce alkalmazásban, amikor az értékelések és vélemények modulok a PDP-ken való megjelenítésre vannak konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="fe8a9-140">![PDP-sablon, ha az értékelések és vélemények a PDP-n történő megjelenítésre vannak konfigurálva.](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="fe8a9-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="fe8a9-141">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-141">Product reviews list module</span></span>

<span data-ttu-id="fe8a9-142">A termékvélemények listája modul felsorolja a termékkel kapcsolatos véleményeket rendezési, szűrési és tördelési beállításokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="fe8a9-143">Ez a modul a PDP-n általában egy értékelési hisztogram modul után jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="fe8a9-144">A következő táblázat bemutatja a termékvélemények listája modul tulajdonságokat, amelyeket a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="fe8a9-145">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="fe8a9-145">Property name</span></span>              | <span data-ttu-id="fe8a9-146">Érték</span><span class="sxs-lookup"><span data-stu-id="fe8a9-146">Value</span></span> | <span data-ttu-id="fe8a9-147">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="fe8a9-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="fe8a9-148">Az egyes oldalakon megjelenített vélemények</span><span class="sxs-lookup"><span data-stu-id="fe8a9-148">Reviews shown on each page</span></span> | <span data-ttu-id="fe8a9-149">10</span><span class="sxs-lookup"><span data-stu-id="fe8a9-149">10</span></span>    | <span data-ttu-id="fe8a9-150">Egy PDP-n egyidejűleg megjelenített vélemények száma.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="fe8a9-151">A **Következő** és **Előző** gomb segítségével a felhasználók a véleményeket tartalmazó lapok között navigálhatnak.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="fe8a9-152">Értékelési hisztogram – Összesítő nézet</span><span class="sxs-lookup"><span data-stu-id="fe8a9-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="fe8a9-153">A termékvélemények listája modul tartalmaz egy olyan helyet, ahol hozzáadhat egy értékelési hisztogram modult.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="fe8a9-154">A következő ábra azt mutatja be, hogyan lehet az értékelési hisztogram modult hozzáadni a termékvélemények listája modulhoz a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Értékelési hisztogram modul hozzáadása egy termékvélemények listája modulhoz](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="fe8a9-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fe8a9-156">Additional resources</span></span>

[<span data-ttu-id="fe8a9-157">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="fe8a9-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="fe8a9-158">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="fe8a9-159">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="fe8a9-160">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="fe8a9-161">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="fe8a9-162">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="fe8a9-163">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="fe8a9-163">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]