---
title: Navigációs menü modulja
description: Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761394"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="ea5e7-103">Navigációs menü modulja</span><span class="sxs-lookup"><span data-stu-id="ea5e7-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="ea5e7-104">Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ea5e7-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ea5e7-105">Overview</span></span>

<span data-ttu-id="ea5e7-106">A navigációs menü modulok elsődleges célja, hogy a webhely felhasználói a Dynamics 365 Commerce központban megadott csatorna-navigációs hierarchia alapján böngésszék a termékeket és a weboldalakat.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="ea5e7-107">A navigációs menü modulban konfigurált cikkek a webhely fejlécének navigációs részeként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="ea5e7-108">A navigációs menü modulok olyan statikus menüelemeket is támogatnak, amelyek az e-commerce webhely más lapjaira hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="ea5e7-109">A navigációs menü modul hozzáadható a lap fejlécmoduljához.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="ea5e7-110">A Fabrikam témában a navigációs menü alapértelmezés szerint két szintet mutat.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="ea5e7-111">A Keudő témában a navigációs menü alapértelmezés szerint három szintet mutat.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="ea5e7-112">Ha módosítani szeretné a szintek számát, a témában egy nézetbővítmény szükséges.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="ea5e7-113">A következő ábra egy navigációs menüt mutat be a Fabrikam, webhelyen, amely két szintű kategória-hierarchiát és néhány statikus menüelemet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="ea5e7-114">![Példa egy navigációs menü modulra](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="ea5e7-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="ea5e7-115">Navigációs menü moduljának tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="ea5e7-115">Navigation menu module properties</span></span>

| <span data-ttu-id="ea5e7-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="ea5e7-116">Property name</span></span>             | <span data-ttu-id="ea5e7-117">Érték</span><span class="sxs-lookup"><span data-stu-id="ea5e7-117">Value</span></span>                 | <span data-ttu-id="ea5e7-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="ea5e7-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="ea5e7-119">Forrás</span><span class="sxs-lookup"><span data-stu-id="ea5e7-119">Source</span></span>                  | <span data-ttu-id="ea5e7-120">**Kiskereskedelem**, **Kézi szerkesztés**, **Kiskereskedelem és kézi készítés**</span><span class="sxs-lookup"><span data-stu-id="ea5e7-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="ea5e7-121">A **Kiskereskedelem** érték lehetővé teszi a csatorna navigációs hierarchiájának megjelenítését a Commerce központból a navigációs menüben.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="ea5e7-122">A **Manuális szerkesztés** érték lehetővé teszi a statikus menüelemek válogatását.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="ea5e7-123">A **Kiskereskedelem és a manuális szerkesztés** érték a kettő kombinációját is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="ea5e7-124">Kategóriaképek megjelenítése</span><span class="sxs-lookup"><span data-stu-id="ea5e7-124">Show category images</span></span> | <span data-ttu-id="ea5e7-125">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="ea5e7-125">**True** or **False**</span></span>    | <span data-ttu-id="ea5e7-126">Ha ez a tulajdonság engedélyezve van, megjeleníti a kategóriaképeket a navigációs menüben, ahogy az definiálva van a Commerce központban az egyes kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="ea5e7-127">Hozzáadva a Commerce 10.0.14-es kiadásában.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="ea5e7-128">Statikus menüelem</span><span class="sxs-lookup"><span data-stu-id="ea5e7-128">Static menu item</span></span>| <span data-ttu-id="ea5e7-129">Értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="ea5e7-129">Array of values</span></span>| <span data-ttu-id="ea5e7-130">A statikus menüelemek menüelemek nevét társítják egy statikus webhely-lapra mutató hivatkozással.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="ea5e7-131">A menüelemek más menüelemek alatt is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="ea5e7-132">Alapértelmezés szerint a statikus menük a gyökér szintjén jelennek meg, és a csatorna navigációs hierarchiához lesznek hozzáfűzve, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="ea5e7-133">A következő ábra egy példát mutat be egy kategóriakép megjelenítésére a Fabrikam webhely navigációs menüjében.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="ea5e7-134">![Példa egy navigációs menü moduljára a kategóriaképekkel](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="ea5e7-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="ea5e7-135">Navigációs menümodul hozzáadása a fejléc modulhoz</span><span class="sxs-lookup"><span data-stu-id="ea5e7-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="ea5e7-136">A navigációs menü modulnak a fejléc-modulba való felvételével kapcsolatos részleteket lásd a [Fejléc modul](author-header-module.md) részben.</span><span class="sxs-lookup"><span data-stu-id="ea5e7-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea5e7-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ea5e7-137">Additional resources</span></span>

[<span data-ttu-id="ea5e7-138">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="ea5e7-138">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ea5e7-139">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="ea5e7-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ea5e7-140">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="ea5e7-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="ea5e7-141">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="ea5e7-141">Header module</span></span>](author-header-module.md)
