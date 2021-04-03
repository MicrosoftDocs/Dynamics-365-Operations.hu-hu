---
title: A Cikk felvétele beállítás nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az üzletben való felvétel lehetősége nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c78dee7289931cecd0f2d7c09caf7881eb8cfd23
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585354"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="2a489-103">A Cikk felvétele beállítás nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon</span><span class="sxs-lookup"><span data-stu-id="2a489-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a489-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az üzletben való felvétel lehetősége nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon.</span><span class="sxs-lookup"><span data-stu-id="2a489-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="2a489-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="2a489-105">Description</span></span>

<span data-ttu-id="2a489-106">A **Cikk felvétele** gomb nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon.</span><span class="sxs-lookup"><span data-stu-id="2a489-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="2a489-107">A következő ábra egy olyan oldal példáját mutatja be, amely tartalmazza a **Cikk felvétele** gombot.</span><span class="sxs-lookup"><span data-stu-id="2a489-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Cikk felvétele gomb](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="2a489-109">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2a489-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="2a489-110">A BOPIS-bővítmény engedélyezése a Commerce webhelyszerkesztőben</span><span class="sxs-lookup"><span data-stu-id="2a489-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="2a489-111">Az „online vásárlás, átvétel az áruházban” (BOPIS) bővítmény Commerce webhelyszerkesztőben történő engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2a489-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2a489-112">Válassza ki a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="2a489-112">Select your site.</span></span>
1. <span data-ttu-id="2a489-113">Válassza a **Webhelybeállítások** lehetőséget, majd válassza ki a **Bővítmények** pontot.</span><span class="sxs-lookup"><span data-stu-id="2a489-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="2a489-114">Győződjön meg arról, hogy a **BOPIS letiltása** lehetőség ne legyen bejelölve.</span><span class="sxs-lookup"><span data-stu-id="2a489-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="2a489-115">Szállítási módok konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="2a489-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="2a489-116">A szállítási módok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2a489-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="2a489-117">Ugrás ide: **Beszerzés és forrás \> Beállítás \> Szállítási módok**.</span><span class="sxs-lookup"><span data-stu-id="2a489-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="2a489-118">Győződjön meg arról, hogy létrejött egy **Vevői átvétel** mód, és termékek és címek vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="2a489-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="2a489-119">Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="2a489-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="2a489-120">A bal oldali navigációs ablakban válassza ki a **Vevői rendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a489-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="2a489-121">Győződjön meg arról, hogy az **Átvételi szállítási mód** helyesen legyen konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="2a489-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="2a489-122">Vevői rendelések kifizetésének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2a489-122">Configure customer orders payments</span></span>

<span data-ttu-id="2a489-123">A vevői rendelések kifizetésének Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2a489-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="2a489-124">Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="2a489-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="2a489-125">A bal oldali navigációs ablakban válassza ki a **Vevői rendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a489-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="2a489-126">A **Kifizetések** gyorslapon ellenőrizze, hogy helyesen vannak-e beállítva a **Fizetési feltételek** és a **Fizetési mód** mezők.</span><span class="sxs-lookup"><span data-stu-id="2a489-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a489-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2a489-127">Additional resources</span></span>

[<span data-ttu-id="2a489-128">BOPIS konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2a489-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="2a489-129">Több felvételi szállítási mód engedélyezése a vevői rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="2a489-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="2a489-130">Omni-channel Commerce rendelési kifizetések</span><span class="sxs-lookup"><span data-stu-id="2a489-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="2a489-131">Üzletválasztó modul</span><span class="sxs-lookup"><span data-stu-id="2a489-131">Store selector module</span></span>](../store-selector.md)
