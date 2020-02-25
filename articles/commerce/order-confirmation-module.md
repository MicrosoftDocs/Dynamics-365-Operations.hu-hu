---
title: Rendelési részletek modul
description: Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026017"
---
# <a name="order-details-module"></a><span data-ttu-id="0eb73-103">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="0eb73-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0eb73-104">Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="0eb73-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0eb73-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0eb73-105">Overview</span></span>

<span data-ttu-id="0eb73-106">A rendelési részletek modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően.</span><span class="sxs-lookup"><span data-stu-id="0eb73-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="0eb73-107">Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat és a szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="0eb73-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="0eb73-108">A Rendelés-megerősítési modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="0eb73-108">Order confirmation module properties</span></span>

| <span data-ttu-id="0eb73-109">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="0eb73-109">Property name</span></span>  | <span data-ttu-id="0eb73-110">Értékek</span><span class="sxs-lookup"><span data-stu-id="0eb73-110">Values</span></span> | <span data-ttu-id="0eb73-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="0eb73-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="0eb73-112">Címsor</span><span class="sxs-lookup"><span data-stu-id="0eb73-112">Heading</span></span>        | <span data-ttu-id="0eb73-113">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="0eb73-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="0eb73-114">A rendelés-megerősítési modulnak lehet fejléce.</span><span class="sxs-lookup"><span data-stu-id="0eb73-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="0eb73-115">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="0eb73-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="0eb73-116">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="0eb73-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="0eb73-117">Kapcsolattartási telefonszám</span><span class="sxs-lookup"><span data-stu-id="0eb73-117">Contact number</span></span> | <span data-ttu-id="0eb73-118">Text</span><span class="sxs-lookup"><span data-stu-id="0eb73-118">Text</span></span> | <span data-ttu-id="0eb73-119">A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg.</span><span class="sxs-lookup"><span data-stu-id="0eb73-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="0eb73-120">A rendelési részletek oldalon használható modulok</span><span class="sxs-lookup"><span data-stu-id="0eb73-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="0eb73-121">A rendelési részletek oldal létrehozásakor a rendelési részletek modul mellett további releváns modulok is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="0eb73-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="0eb73-122">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="0eb73-122">Here are some examples:</span></span>

- <span data-ttu-id="0eb73-123">**Javaslatok modul** – A javaslatok modul hozzáadható a rendelési részletek oldalhoz, hogy a vevőnek más termékeket ajánljon fel.</span><span class="sxs-lookup"><span data-stu-id="0eb73-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="0eb73-124">**Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési részletek oldalhoz, hogy marketingtartalmakat jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="0eb73-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="0eb73-125">Rendelési részletek oldalmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="0eb73-125">Create an order details page module</span></span>

1. <span data-ttu-id="0eb73-126">Hozzon létre egy **Rendelési részletek sablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="0eb73-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="0eb73-127">Az alapértelmezett lap **Fő** helyén adjon hozzá egy rendelési részletek modult.</span><span class="sxs-lookup"><span data-stu-id="0eb73-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="0eb73-128">A rendelési részletek modulban vegyen fel egy ajánlási modult.</span><span class="sxs-lookup"><span data-stu-id="0eb73-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="0eb73-129">Mentse a sablont, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="0eb73-129">Save and preview the template.</span></span> <span data-ttu-id="0eb73-130">A rendelési részletek modul nem kerül megjelenítésre, mert szükséges hozzá a rendelés megerősítési számának a környezete.</span><span class="sxs-lookup"><span data-stu-id="0eb73-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="0eb73-131">Fejezze be a sablon szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="0eb73-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="0eb73-132">A most létrehozott rendelési részletek sablon használatával hozzon létre egy **rendelési részletek oldal** nevű oldalt.</span><span class="sxs-lookup"><span data-stu-id="0eb73-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="0eb73-133">Adja hozzá az alapértelmezett lapot a lap struktúrájához.</span><span class="sxs-lookup"><span data-stu-id="0eb73-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="0eb73-134">Adja meg a fejléc-töredéket a **Fejléc** bővítőhelyén.</span><span class="sxs-lookup"><span data-stu-id="0eb73-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="0eb73-135">Adja meg a lábléc-töredéket a **Lábléc** bővítőhelyén.</span><span class="sxs-lookup"><span data-stu-id="0eb73-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="0eb73-136">A **Fő** bővítőhelyen adjon hozzá egy rendelési rézletek modult.</span><span class="sxs-lookup"><span data-stu-id="0eb73-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="0eb73-137">A rendelési részletek modul tulajdonságlapjához adja hozzá a **Rendelési részletek** fejlécet.</span><span class="sxs-lookup"><span data-stu-id="0eb73-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="0eb73-138">A rendelési részletek modul alatt vegyen fel egy ajánlási modult, és konfigurálja úgy, hogy az **Új** és **Legkelendőbb** beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="0eb73-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="0eb73-139">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="0eb73-139">Save and preview the page.</span></span>
1. <span data-ttu-id="0eb73-140">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="0eb73-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0eb73-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0eb73-141">Additional resources</span></span>

[<span data-ttu-id="0eb73-142">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="0eb73-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0eb73-143">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="0eb73-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0eb73-144">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="0eb73-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0eb73-145">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="0eb73-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0eb73-146">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="0eb73-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0eb73-147">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="0eb73-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0eb73-148">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="0eb73-148">Footer module</span></span>](author-footer-module.md)
