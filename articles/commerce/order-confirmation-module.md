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
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257147"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="4b63b-103">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b63b-104">Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket használni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4b63b-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4b63b-105">A rendelési visszaigazolás modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően.</span><span class="sxs-lookup"><span data-stu-id="4b63b-105">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="4b63b-106">Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat, az átvételi beállításokat és a szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="4b63b-106">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="4b63b-107">A Rendelés-megerősítési modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="4b63b-107">Order confirmation module properties</span></span>

| <span data-ttu-id="4b63b-108">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="4b63b-108">Property name</span></span>  | <span data-ttu-id="4b63b-109">Értékek</span><span class="sxs-lookup"><span data-stu-id="4b63b-109">Values</span></span> | <span data-ttu-id="4b63b-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="4b63b-110">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="4b63b-111">Címsor</span><span class="sxs-lookup"><span data-stu-id="4b63b-111">Heading</span></span>        | <span data-ttu-id="4b63b-112">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="4b63b-112">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="4b63b-113">A rendelés-megerősítési modulnak lehet fejléce.</span><span class="sxs-lookup"><span data-stu-id="4b63b-113">The order confirmation module can have a heading.</span></span> <span data-ttu-id="4b63b-114">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="4b63b-114">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="4b63b-115">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b63b-115">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="4b63b-116">Kapcsolattartási telefonszám</span><span class="sxs-lookup"><span data-stu-id="4b63b-116">Contact number</span></span> | <span data-ttu-id="4b63b-117">Text</span><span class="sxs-lookup"><span data-stu-id="4b63b-117">Text</span></span> | <span data-ttu-id="4b63b-118">A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg.</span><span class="sxs-lookup"><span data-stu-id="4b63b-118">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="4b63b-119">Felvételi időköz adatainak megjelenítése</span><span class="sxs-lookup"><span data-stu-id="4b63b-119">Show pickup timeslot information</span></span> | <span data-ttu-id="4b63b-120">Igaz vagy hamis</span><span class="sxs-lookup"><span data-stu-id="4b63b-120">True or False</span></span> | <span data-ttu-id="4b63b-121">A tulajdonság a Dynamics 365 Commerce 10.0.15-ös vagy újabb verziókban áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="4b63b-121">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="4b63b-122">Ha ez igaz, akkor megjeleníti a felvételi időközzel kapcsolatos információkat, ha egy felvételi cikkhez van megadva</span><span class="sxs-lookup"><span data-stu-id="4b63b-122">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="4b63b-123">A rendelési visszaigazolás oldalon használható modulok</span><span class="sxs-lookup"><span data-stu-id="4b63b-123">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="4b63b-124">A rendelési visszaigazolás oldal létrehozásakor a rendelési visszaigazolás modul mellett további releváns modulok is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="4b63b-124">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="4b63b-125">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="4b63b-125">Here are some examples:</span></span>

- <span data-ttu-id="4b63b-126">**Javaslatok modul** – A javaslatok modul hozzáadható a rendelési visszaigazolás oldalhoz, hogy a vevőnek más termékeket ajánljon fel.</span><span class="sxs-lookup"><span data-stu-id="4b63b-126">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="4b63b-127">**Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési visszaigazolás oldalhoz, hogy marketingtartalmakat jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="4b63b-127">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="4b63b-128">Rendelés visszaigazolás modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="4b63b-128">Add an order confirmation module to a page</span></span>

<span data-ttu-id="4b63b-129">A rendelés visszaigazolás modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4b63b-129">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="4b63b-130">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-130">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="4b63b-131">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Rendelés visszaigazolási sablon** nevet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="4b63b-131">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-132">A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-132">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4b63b-133">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4b63b-133">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-134">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-134">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4b63b-135">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4b63b-135">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-136">Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-136">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="4b63b-137">A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.</span><span class="sxs-lookup"><span data-stu-id="4b63b-137">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="4b63b-138">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="4b63b-138">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4b63b-139">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4b63b-139">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="4b63b-140">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Rendelési visszaigazolási sablont**.</span><span class="sxs-lookup"><span data-stu-id="4b63b-140">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="4b63b-141">Az **Oldal neve** alatta adja meg a **Rendelés visszaigazolás oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4b63b-141">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-142">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-142">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4b63b-143">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4b63b-143">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-144">A rendelés visszaigazolása modul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-144">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="4b63b-145">A **Címsor** párbeszédpanel **Címsor szövege** mezőjébe írja be a **Rendelés visszaigazolása** címsorszöveget, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="4b63b-145">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="4b63b-146">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b63b-146">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="4b63b-147">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="4b63b-147">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b63b-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4b63b-148">Additional resources</span></span>

[<span data-ttu-id="4b63b-149">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="4b63b-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4b63b-150">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-150">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="4b63b-151">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="4b63b-151">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4b63b-152">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-152">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="4b63b-153">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-153">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="4b63b-154">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-154">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="4b63b-155">Átvételi információ modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-155">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="4b63b-156">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="4b63b-156">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]