---
title: Értékelések és vélemények modulok
description: Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain használt minősítési és az értékelési modulokat tárgyalja.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
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
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 85fb1272103eed7d6e44635b7c20438471d96b34
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412963"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="47817-103">Értékelések és vélemények modulok</span><span class="sxs-lookup"><span data-stu-id="47817-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47817-104">Ez a témakör a Microsoft Dynamics 365 Commerce termékrészletek oldalain (PDP-k) használt minősítési és az értékelési modulokat tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="47817-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="47817-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="47817-105">Overview</span></span>

<span data-ttu-id="47817-106">Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, ugyanakkor egy módszert jelentenek a termékkel kapcsolatos ügyfél-visszajelzések gyűjtésére.</span><span class="sxs-lookup"><span data-stu-id="47817-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="47817-107">Az értékelések a termék listaoldalakon, kategória listaoldalakon, a keresési találatok oldalain és a webhely más oldalain jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="47817-107">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="47817-108">Az értékelési hisztogramok és a termékértékelések a PDP-ken jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="47817-108">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="47817-109">A **Vélemény írása** gombra kattintva a vevők elküldhetik a termékkel kapcsolatos értékeléseket és véleményeket.</span><span class="sxs-lookup"><span data-stu-id="47817-109">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="47817-110">Ezeket a PDP-funkciókat a minősítési és a felülvizsgálati modulok vezérlik.</span><span class="sxs-lookup"><span data-stu-id="47817-110">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="47817-111">Értékelések és vélemények modulok a PDP-ken</span><span class="sxs-lookup"><span data-stu-id="47817-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="47817-112">Három modul mutatja az értékelések és vélemények összesítését a PDP-ken:</span><span class="sxs-lookup"><span data-stu-id="47817-112">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="47817-113">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="47817-113">Write review module</span></span>
- <span data-ttu-id="47817-114">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="47817-114">Product reviews list module</span></span>
- <span data-ttu-id="47817-115">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="47817-115">Ratings histogram module</span></span>
 
<span data-ttu-id="47817-116">A következő ábra bemutatja, hogyan jelennek meg az értékelések és vélemények modulok egy PDP-n.</span><span class="sxs-lookup"><span data-stu-id="47817-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Értékelések és vélemények modulok a PDP-ken](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="47817-118">Ha további tájékoztatást szeretne kapni a PDP-sablonok és -elrendezések optimalizálásával kapcsolatban, hogy az e-kereskedelmi webhelyének több PDP-je között megoszthassa az értékelések és vélemények modulok konfigurációit, tekintse meg a következőt: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="47817-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="47817-119">A következő ábra bemutatja, hogyan mutatja be a **Modul hozzáadása** párbeszédpanel az értékelések és vélemények modulokat a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="47817-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="47817-120">![Modul hozzáadása párbeszédpanel](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="47817-120">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="47817-121">Vélemény írása modul</span><span class="sxs-lookup"><span data-stu-id="47817-121">Write review module</span></span>

<span data-ttu-id="47817-122">A vélemény írása modul egy **Vélemény írása** gombot tartalmaz, amely lehetővé teszi a felhasználók számára a bejelentkezést, egy értékelés hozzárendelését és a termékkel kapcsolatos vélemény megírását.</span><span class="sxs-lookup"><span data-stu-id="47817-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="47817-123">Ez a modul azt is lehetővé teszi, hogy a felhasználók szerkesszék a korábban elküldött értékelést vagy véleményt.</span><span class="sxs-lookup"><span data-stu-id="47817-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="47817-124">Ez a modul általában az értékelési hisztogram és a termékvélemények listájának moduljai fölött jelenik meg a PDP-ben.</span><span class="sxs-lookup"><span data-stu-id="47817-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="47817-125">A következő ábra bemutatja, hogyan jeleníti meg a **Vélemény írása** párbeszédpanel, amikor a vevő a **Vélemény írása** lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="47817-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="47817-126">A vevő ezt a párbeszédpanelt használhatja az értékelés és vélemény elküldésére.</span><span class="sxs-lookup"><span data-stu-id="47817-126">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="47817-127">![Értékelés írása párbeszédablak](media/rnr-eCommerce-write-review-module.png) A következő táblázat bemutatja a vélemény írása modul tulajdonságot, amelyet a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="47817-127">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="47817-128">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="47817-128">Property name</span></span> | <span data-ttu-id="47817-129">Érték</span><span class="sxs-lookup"><span data-stu-id="47817-129">Value</span></span>        | <span data-ttu-id="47817-130">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="47817-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="47817-131">Név</span><span class="sxs-lookup"><span data-stu-id="47817-131">Name</span></span>          | <span data-ttu-id="47817-132">Vélemény írása</span><span class="sxs-lookup"><span data-stu-id="47817-132">Write review</span></span> | <span data-ttu-id="47817-133">A vélemény írása modul neve.</span><span class="sxs-lookup"><span data-stu-id="47817-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="47817-134">Értékelési hisztogram modul</span><span class="sxs-lookup"><span data-stu-id="47817-134">Ratings histogram module</span></span>

<span data-ttu-id="47817-135">Az értékelési hisztogram modul az értékelések hisztogramját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="47817-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="47817-136">Ez a modul általában a vélemény írása modul és a termékvélemények listája modul között jelenik meg a PDP-n.</span><span class="sxs-lookup"><span data-stu-id="47817-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="47817-137">Az értékelési hisztogram modul nem igényel konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="47817-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="47817-138">Csak fel kell vennie a modult a PDP-sablonba.</span><span class="sxs-lookup"><span data-stu-id="47817-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="47817-139">A következő illusztrációk azt mutatják, hogy milyen egy PDP-sablon a Dynamics 365 Commerce alkalmazásban, amikor az értékelések és vélemények modulok a PDP-ken való megjelenítésre vannak konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="47817-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="47817-140">![PDP-sablon, ha az értékelések és vélemények a PDP-n történő megjelenítésre vannak konfigurálva.](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="47817-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="47817-141">Termékvélemény-lista modul</span><span class="sxs-lookup"><span data-stu-id="47817-141">Product reviews list module</span></span>

<span data-ttu-id="47817-142">A termékvélemények listája modul felsorolja a termékkel kapcsolatos véleményeket rendezési, szűrési és tördelési beállításokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="47817-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="47817-143">Ez a modul a PDP-n általában egy értékelési hisztogram modul után jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="47817-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="47817-144">A következő táblázat bemutatja a termékvélemények listája modul tulajdonságokat, amelyeket a szerkesztési eszközben konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="47817-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="47817-145">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="47817-145">Property name</span></span>              | <span data-ttu-id="47817-146">Érték</span><span class="sxs-lookup"><span data-stu-id="47817-146">Value</span></span> | <span data-ttu-id="47817-147">Tulajdonság leírása</span><span class="sxs-lookup"><span data-stu-id="47817-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="47817-148">Az egyes oldalakon megjelenített vélemények</span><span class="sxs-lookup"><span data-stu-id="47817-148">Reviews shown on each page</span></span> | <span data-ttu-id="47817-149">10</span><span class="sxs-lookup"><span data-stu-id="47817-149">10</span></span>    | <span data-ttu-id="47817-150">Egy PDP-n egyidejűleg megjelenített vélemények száma.</span><span class="sxs-lookup"><span data-stu-id="47817-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="47817-151">A **Következő** és **Előző** gomb segítségével a felhasználók a véleményeket tartalmazó lapok között navigálhatnak.</span><span class="sxs-lookup"><span data-stu-id="47817-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="47817-152">Értékelési hisztogram – Összesítő nézet</span><span class="sxs-lookup"><span data-stu-id="47817-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="47817-153">A termékvélemények listája modul tartalmaz egy olyan helyet, ahol hozzáadhat egy értékelési hisztogram modult.</span><span class="sxs-lookup"><span data-stu-id="47817-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="47817-154">A következő ábra azt mutatja be, hogyan lehet az értékelési hisztogram modult hozzáadni a termékvélemények listája modulhoz a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="47817-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Értékelési hisztogram modul hozzáadása egy termékvélemények listája modulhoz](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="47817-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="47817-156">Additional resources</span></span>

[<span data-ttu-id="47817-157">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="47817-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="47817-158">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="47817-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="47817-159">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="47817-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="47817-160">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="47817-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="47817-161">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="47817-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="47817-162">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="47817-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="47817-163">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="47817-163">Footer module</span></span>](author-footer-module.md)
