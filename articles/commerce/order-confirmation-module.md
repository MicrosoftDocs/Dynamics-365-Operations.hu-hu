---
title: Rendelésmegerősítési modul
description: Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698326"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="87261-103">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="87261-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="87261-104">Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="87261-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="87261-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="87261-105">Overview</span></span>

<span data-ttu-id="87261-106">A rendelésmegerősítési modul egy rendelés megerősítő lapján megjelenő visszaigazoló üzenet megjelenítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="87261-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="87261-107">A rendelésmegerősítési modul megjeleníti a rendelés visszaigazolási számát és a pénztárnál megadott vevői e-mail címet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="87261-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="87261-108">Amikor egy rendelést leadják a pénztárnál, a rendelés visszaigazolásának számát és a vevő e-mail címét a program a lap URL-címében egy lekérdezési karakterláncként adja át a rendelés visszaigazolási lapjának.</span><span class="sxs-lookup"><span data-stu-id="87261-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="87261-109">A rendelés megerősítési modulja megkapja ezeket az adatokat, és a rendelés visszaigazolási oldalán megjeleníti a rendelés állapotát.</span><span class="sxs-lookup"><span data-stu-id="87261-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="87261-110">A rendelésmegerősítési modulnak szükséges ez az oldalkörnyezet rendelés állapotának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="87261-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="87261-111">A Rendelés-megerősítési modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="87261-111">Order confirmation module properties</span></span>

| <span data-ttu-id="87261-112">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="87261-112">Property name</span></span> | <span data-ttu-id="87261-113">Értékek</span><span class="sxs-lookup"><span data-stu-id="87261-113">Values</span></span> | <span data-ttu-id="87261-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="87261-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="87261-115">Címsor</span><span class="sxs-lookup"><span data-stu-id="87261-115">Heading</span></span>       | <span data-ttu-id="87261-116">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="87261-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="87261-117">A rendelés-megerősítési modulnak lehet fejléce.</span><span class="sxs-lookup"><span data-stu-id="87261-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="87261-118">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="87261-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="87261-119">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="87261-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="87261-120">A rendelés-visszaigazolási lapmodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="87261-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="87261-121">**Javaslatok** – A javaslatok modul elhelyezhető a rendelés megerősítő lapjára, hogy a vevőnek más termékeket ajánlhat fel.</span><span class="sxs-lookup"><span data-stu-id="87261-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="87261-122">**Marketing** – a marketing modul marketing tartalmat adhat a rendelés megerősítésének lapjához.</span><span class="sxs-lookup"><span data-stu-id="87261-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="87261-123">Rendelés-visszaigazolási oldal létrehozása</span><span class="sxs-lookup"><span data-stu-id="87261-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="87261-124">Hozzon létre egy **rendelés megerősítési sablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="87261-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="87261-125">Az alapértelmezett lap **Fő** helyén adjon hozzá egy rendelés megerősítése modult.</span><span class="sxs-lookup"><span data-stu-id="87261-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="87261-126">A rendelés megerősítése modulban vegyen fel egy ajánlási modult.</span><span class="sxs-lookup"><span data-stu-id="87261-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="87261-127">Mentse a sablont, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="87261-127">Save and preview the template.</span></span> <span data-ttu-id="87261-128">A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.</span><span class="sxs-lookup"><span data-stu-id="87261-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="87261-129">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="87261-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="87261-130">A most létrehozott rendelés megerősítése sablon használatával hozzon létre egy **rendelés megerősítése** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="87261-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="87261-131">Adja hozzá az alapértelmezett lapot a lap struktúrájához.</span><span class="sxs-lookup"><span data-stu-id="87261-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="87261-132">Adja meg a fejléc-töredéket a **Fejléc** bővítőhelyén.</span><span class="sxs-lookup"><span data-stu-id="87261-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="87261-133">Adja meg a lábléc-töredéket a **Lábléc** bővítőhelyén.</span><span class="sxs-lookup"><span data-stu-id="87261-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="87261-134">A **Fő** bővítőhelyen adjon hozzá egy rendelés megerősítése modult.</span><span class="sxs-lookup"><span data-stu-id="87261-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="87261-135">A rendelés-visszaigazolási modul tulajdonságlapjához adja hozzá a **Rendelés megerősítése** fejlécet.</span><span class="sxs-lookup"><span data-stu-id="87261-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="87261-136">A rendelés-visszaigazolási modul alatt vegyen fel egy ajánlási modult, és konfigurálja úgy, hogy az **Új** és **Legkelendőbb** beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="87261-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="87261-137">Mentse az oldalt és tekintse meg előnézetét, adja be és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="87261-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87261-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="87261-138">Additional resources</span></span>

[<span data-ttu-id="87261-139">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="87261-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="87261-140">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="87261-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="87261-141">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="87261-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="87261-142">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="87261-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="87261-143">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="87261-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="87261-144">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="87261-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="87261-145">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="87261-145">Footer module</span></span>](author-footer-module.md)
