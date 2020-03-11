---
title: Minősítések és értékelések konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
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
ms.openlocfilehash: edd2082b5d2cafcb955f8e3c7762bcba523ac479
ms.sourcegitcommit: 0dace221e8874021dd212271567666f717d39793
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2020
ms.locfileid: "3071566"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="8eb1f-103">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8eb1f-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8eb1f-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni az e-kereskedelmi webhelyet a vevőértékelések megjelenítésére a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8eb1f-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="8eb1f-105">Overview</span></span>

<span data-ttu-id="8eb1f-106">Az e-kereskedelmi webhelyek minősítései és értékelései segítik a vevőket a termékek beszerzési döntés előtt történő megismerésében, és megmutatják, hogy egyéb vevők mit gondolnak ezekről a termékekről.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="8eb1f-107">Az e-kereskedelmi webhelyek esetében a minősítések és értékelések a termékekkel kapcsolatos vevői visszajelzések összegyűjtésének mechanizmusai is egyben.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="8eb1f-108">A webhely konfigurálása értékelések és vélemények megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="8eb1f-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="8eb1f-109">Az értékelések és vélemények értékeinek konfigurációs értékei, például a bérlőazonosító, a vélemény szövegének hossza és a vélemény címének hossza, a webhely szintjén konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="8eb1f-110">Tegye a következőket a webhely konfigurálásához az értékelések és vélemények megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="8eb1f-111">Lépjen a **Kezdőlap \> Webhelyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="8eb1f-112">Válassza ki a webhely nevét.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="8eb1f-113">Ugrás a **Webhelybeállítások \> Bővítmények** pontra.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="8eb1f-114">A **Vélemény szövegének maximális hossza** mezőbe írja be, hogy a vélemények szövege legfeljebb hány karakterből állhat (például **1000**).</span><span class="sxs-lookup"><span data-stu-id="8eb1f-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="8eb1f-115">A **Vélemény címének maximális hossza** mezőbe írja be, hogy a vélemények címei legfeljebb hány karakterből állhatnak (például **55**).</span><span class="sxs-lookup"><span data-stu-id="8eb1f-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="8eb1f-116">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="8eb1f-117">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Webhely konfigurálása értékelések és vélemények megjelenítésére](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="8eb1f-119">Termékértékelés hivatkozása egy PDP Vélemények szakaszához.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="8eb1f-120">A termékértékelés a termék címe alatt jelenik meg a PDP felső részén.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="8eb1f-121">A termékértékelés konfigurálható úgy, hogy az ugyanannak a PDP-nek az **Vélemények** szakaszához legyen társítva.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="8eb1f-122">Egy termékértékelésnek a PDP **Vélemények** szakaszához való társításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="8eb1f-123">Nyissa meg a PDP-sablont.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="8eb1f-124">Lépjen a **Vásárlásmező tárolómoduljának beállításai** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="8eb1f-125">A **Vásárlásmező** alatt válassza ki a **Termékértékelések** elemet, majd válassza a **Kattintás hivatkozása a teljes vélemények modulhoz** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="8eb1f-126">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Termékértékelés hivatkozása egy PDP Vélemények szakaszához](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="8eb1f-128">Az adatvédelem és irányelvek lap hivatkozásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8eb1f-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="8eb1f-129">Az adatvédelem és irányelvek lap hivatkozásának konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="8eb1f-130">Lépjen a **Kezdőlap \> Webhelyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="8eb1f-131">Válassza ki a webhely nevét.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="8eb1f-132">Ugrás a **Webhelybeállítások \> Bővítmények** pontra.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="8eb1f-133">Az **Útvonalak** lapon az **RNR adatvédelem és irányelvek** alatt válassza a **Hivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="8eb1f-134">Ha már meg van adva egy hivatkozás, és ki szeretné cserélni, válassza ki a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="8eb1f-135">A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az adatvédelem és irányelvek lap hivatkozását, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="8eb1f-136">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="8eb1f-137">Az alábbi ábra azt mutatja, hogyan néz ki ez a konfiguráció a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Az adatvédelem és irányelvek lap hivatkozásának konfigurálása](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="8eb1f-139">A Minősítések és értékelések modulok konfigurálása a termék részletes oldalain</span><span class="sxs-lookup"><span data-stu-id="8eb1f-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="8eb1f-140">A Minősítések és értékelések modulok a termék részletei oldalain történő beállításával kapcsolatos tudnivalókat lásd a [Minősítések és értékelések](ratings-reviews-modules.md) modulban.</span><span class="sxs-lookup"><span data-stu-id="8eb1f-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8eb1f-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8eb1f-141">Additional resources</span></span>

[<span data-ttu-id="8eb1f-142">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="8eb1f-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="8eb1f-143">A minősítések és értékelések használatának bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="8eb1f-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="8eb1f-144">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="8eb1f-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="8eb1f-145">A Minősítések és értékelések modulok konfigurálása a termék részletes oldalain</span><span class="sxs-lookup"><span data-stu-id="8eb1f-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="8eb1f-146">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="8eb1f-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
