---
title: Rendelési részletek modul
description: Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 06/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6610d2abe0a1b03ddd763f9a65fc1dab42f1da1b
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015180"
---
# <a name="order-details-module"></a><span data-ttu-id="db85f-103">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="db85f-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db85f-104">Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="db85f-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="db85f-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="db85f-105">Overview</span></span>

<span data-ttu-id="db85f-106">A rendelési részletek modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően.</span><span class="sxs-lookup"><span data-stu-id="db85f-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="db85f-107">Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat és a szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="db85f-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="db85f-108">A Rendelés részletei modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="db85f-108">Order details module properties</span></span>

| <span data-ttu-id="db85f-109">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="db85f-109">Property name</span></span>  | <span data-ttu-id="db85f-110">Értékek</span><span class="sxs-lookup"><span data-stu-id="db85f-110">Values</span></span> | <span data-ttu-id="db85f-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="db85f-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="db85f-112">Címsor</span><span class="sxs-lookup"><span data-stu-id="db85f-112">Heading</span></span>        | <span data-ttu-id="db85f-113">Fejléc szövege és fejléc címkéje ( **H1** , **H2** , **H3** , **H4** , **H5** vagy **H6** )</span><span class="sxs-lookup"><span data-stu-id="db85f-113">Heading text and heading tag ( **H1** , **H2** , **H3** , **H4** , **H5** , or **H6** )</span></span> | <span data-ttu-id="db85f-114">A rendelés részletei modulnak lehet fejléce.</span><span class="sxs-lookup"><span data-stu-id="db85f-114">The order details module can have a heading.</span></span> <span data-ttu-id="db85f-115">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="db85f-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="db85f-116">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="db85f-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="db85f-117">Kapcsolattartási telefonszám</span><span class="sxs-lookup"><span data-stu-id="db85f-117">Contact number</span></span> | <span data-ttu-id="db85f-118">Text</span><span class="sxs-lookup"><span data-stu-id="db85f-118">Text</span></span> | <span data-ttu-id="db85f-119">A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg.</span><span class="sxs-lookup"><span data-stu-id="db85f-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="db85f-120">A rendelési részletek oldalon használható modulok</span><span class="sxs-lookup"><span data-stu-id="db85f-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="db85f-121">A rendelési részletek oldal létrehozásakor a rendelési részletek modul mellett további releváns modulok is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="db85f-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="db85f-122">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="db85f-122">Here are some examples:</span></span>

- <span data-ttu-id="db85f-123">**Javaslatok modul** – A javaslatok modul hozzáadható a rendelési részletek oldalhoz, hogy a vevőnek más termékeket ajánljon fel.</span><span class="sxs-lookup"><span data-stu-id="db85f-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="db85f-124">**Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési részletek oldalhoz, hogy marketingtartalmakat jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="db85f-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="db85f-125">Rendelés részletei modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="db85f-125">Add an order details module to a page</span></span>

<span data-ttu-id="db85f-126">A rendelés részletei modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="db85f-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="db85f-127">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-127">Go to **Templates** , and select **New** to create a new template.</span></span>
1. <span data-ttu-id="db85f-128">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Rendelés részletei** nevet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="db85f-128">In the **New Template** dialog box, under **Template name** , enter the name **Order details template** , and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-129">A **Törzs** helyben válassza a három pont ( **…** ) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-129">In the **Body** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db85f-130">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="db85f-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-131">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont ( **…** ) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-131">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db85f-132">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés részletei** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="db85f-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-133">Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-133">Select **Save** , and then select **Preview** to preview the template.</span></span> <span data-ttu-id="db85f-134">A rendelési részletek modul nem kerül megjelenítésre, mert szükséges hozzá a rendelés megerősítési számának a környezete.</span><span class="sxs-lookup"><span data-stu-id="db85f-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="db85f-135">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="db85f-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="db85f-136">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="db85f-136">Go to **Pages** , and select **New** to create a new page.</span></span>
1. <span data-ttu-id="db85f-137">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Rendelés részletei sablont**.</span><span class="sxs-lookup"><span data-stu-id="db85f-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="db85f-138">Az **Oldal neve** alatta adja meg a **Rendelés részletei oldalt** , majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="db85f-138">Under **Page name** , enter **Order details page** , and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-139">Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont ( **…** ) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-139">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="db85f-140">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés részletei** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="db85f-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-141">A rendelés részletei modul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="db85f-142">A **Címsor** párbeszédpanel **Címsor szövege** mezőjébe írja be a **Rendelés részletei** címsorszöveget, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="db85f-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details** , and then select **OK**.</span></span>
1. <span data-ttu-id="db85f-143">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="db85f-143">Select **Save** , and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="db85f-144">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="db85f-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db85f-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="db85f-145">Additional resources</span></span>

[<span data-ttu-id="db85f-146">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="db85f-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="db85f-147">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="db85f-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="db85f-148">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="db85f-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="db85f-149">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="db85f-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="db85f-150">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="db85f-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="db85f-151">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="db85f-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="db85f-152">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="db85f-152">Gift card module</span></span>](add-giftcard.md)
