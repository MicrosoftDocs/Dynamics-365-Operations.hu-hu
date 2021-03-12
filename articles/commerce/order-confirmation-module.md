---
title: Rendelésmegerősítési modul
description: Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket használni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9d916d2687777403f2b0df7c35171948ad2fb7db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972743"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="3e025-103">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="3e025-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e025-104">Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket használni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3e025-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e025-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="3e025-105">Overview</span></span>

<span data-ttu-id="3e025-106">A rendelési visszaigazolás modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően.</span><span class="sxs-lookup"><span data-stu-id="3e025-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="3e025-107">Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat, az átvételi beállításokat és a szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="3e025-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="3e025-108">A Rendelés-megerősítési modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="3e025-108">Order confirmation module properties</span></span>

| <span data-ttu-id="3e025-109">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="3e025-109">Property name</span></span>  | <span data-ttu-id="3e025-110">Értékek</span><span class="sxs-lookup"><span data-stu-id="3e025-110">Values</span></span> | <span data-ttu-id="3e025-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="3e025-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="3e025-112">Címsor</span><span class="sxs-lookup"><span data-stu-id="3e025-112">Heading</span></span>        | <span data-ttu-id="3e025-113">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="3e025-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="3e025-114">A rendelés-megerősítési modulnak lehet fejléce.</span><span class="sxs-lookup"><span data-stu-id="3e025-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="3e025-115">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="3e025-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="3e025-116">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="3e025-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="3e025-117">Kapcsolattartási telefonszám</span><span class="sxs-lookup"><span data-stu-id="3e025-117">Contact number</span></span> | <span data-ttu-id="3e025-118">Text</span><span class="sxs-lookup"><span data-stu-id="3e025-118">Text</span></span> | <span data-ttu-id="3e025-119">A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg.</span><span class="sxs-lookup"><span data-stu-id="3e025-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="3e025-120">Felvételi időköz adatainak megjelenítése</span><span class="sxs-lookup"><span data-stu-id="3e025-120">Show pickup timeslot information</span></span> | <span data-ttu-id="3e025-121">Igaz vagy hamis</span><span class="sxs-lookup"><span data-stu-id="3e025-121">True or False</span></span> | <span data-ttu-id="3e025-122">A tulajdonság a Dynamics 365 Commerce 10.0.15-ös vagy újabb verziókban áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="3e025-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="3e025-123">Ha ez igaz, akkor megjeleníti a felvételi időközzel kapcsolatos információkat, ha egy felvételi cikkhez van megadva</span><span class="sxs-lookup"><span data-stu-id="3e025-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="3e025-124">A rendelési visszaigazolás oldalon használható modulok</span><span class="sxs-lookup"><span data-stu-id="3e025-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="3e025-125">A rendelési visszaigazolás oldal létrehozásakor a rendelési visszaigazolás modul mellett további releváns modulok is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="3e025-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="3e025-126">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="3e025-126">Here are some examples:</span></span>

- <span data-ttu-id="3e025-127">**Javaslatok modul** – A javaslatok modul hozzáadható a rendelési visszaigazolás oldalhoz, hogy a vevőnek más termékeket ajánljon fel.</span><span class="sxs-lookup"><span data-stu-id="3e025-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="3e025-128">**Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési visszaigazolás oldalhoz, hogy marketingtartalmakat jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="3e025-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="3e025-129">Rendelés visszaigazolás modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="3e025-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="3e025-130">A rendelés visszaigazolás modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3e025-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3e025-131">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3e025-132">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Rendelés visszaigazolási sablon** nevet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="3e025-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-133">A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e025-134">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e025-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-135">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e025-136">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e025-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-137">Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="3e025-138">A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.</span><span class="sxs-lookup"><span data-stu-id="3e025-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="3e025-139">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="3e025-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3e025-140">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="3e025-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="3e025-141">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Rendelési visszaigazolási sablont**.</span><span class="sxs-lookup"><span data-stu-id="3e025-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="3e025-142">Az **Oldal neve** alatta adja meg a **Rendelés visszaigazolás oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e025-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-143">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e025-144">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e025-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-145">A rendelés visszaigazolása modul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="3e025-146">A **Címsor** párbeszédpanel **Címsor szövege** mezőjébe írja be a **Rendelés visszaigazolása** címsorszöveget, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="3e025-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="3e025-147">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e025-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="3e025-148">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="3e025-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e025-149">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3e025-149">Additional resources</span></span>

[<span data-ttu-id="3e025-150">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="3e025-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3e025-151">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="3e025-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="3e025-152">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="3e025-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3e025-153">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="3e025-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="3e025-154">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="3e025-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="3e025-155">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="3e025-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="3e025-156">Átvételi információ modul</span><span class="sxs-lookup"><span data-stu-id="3e025-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="3e025-157">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="3e025-157">Gift card module</span></span>](add-giftcard.md)
