---
title: Navigációs menü modulja
description: Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4412998"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="40b49-103">Navigációs menü modulja</span><span class="sxs-lookup"><span data-stu-id="40b49-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="40b49-104">Ez a témakör a navigációs menü modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="40b49-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="40b49-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="40b49-105">Overview</span></span>

<span data-ttu-id="40b49-106">A navigációs menü modulok elsődleges célja, hogy a webhely felhasználói a Dynamics 365 Commerce központban megadott csatorna-navigációs hierarchia alapján böngésszék a termékeket és a weboldalakat.</span><span class="sxs-lookup"><span data-stu-id="40b49-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="40b49-107">A navigációs menü modulban konfigurált cikkek a webhely fejlécének navigációs részeként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="40b49-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="40b49-108">A navigációs menü modulok olyan statikus menüelemeket is támogatnak, amelyek az e-commerce webhely más lapjaira hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="40b49-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="40b49-109">A navigációs menü modul hozzáadható a lap fejlécmoduljához.</span><span class="sxs-lookup"><span data-stu-id="40b49-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="40b49-110">A Fabrikam témában a navigációs menü alapértelmezés szerint két szintet mutat.</span><span class="sxs-lookup"><span data-stu-id="40b49-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="40b49-111">A Keudő témában a navigációs menü alapértelmezés szerint három szintet mutat.</span><span class="sxs-lookup"><span data-stu-id="40b49-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="40b49-112">Ha módosítani szeretné a szintek számát, a témában egy nézetbővítmény szükséges.</span><span class="sxs-lookup"><span data-stu-id="40b49-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="40b49-113">A következő ábra egy navigációs menüt mutat be a Fabrikam, webhelyen, amely két szintű kategória-hierarchiát és néhány statikus menüelemet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="40b49-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="40b49-114">![Példa egy navigációs menü modulra](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="40b49-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="40b49-115">Navigációs menü moduljának tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="40b49-115">Navigation menu module properties</span></span>

| <span data-ttu-id="40b49-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="40b49-116">Property name</span></span>             | <span data-ttu-id="40b49-117">Érték</span><span class="sxs-lookup"><span data-stu-id="40b49-117">Value</span></span>                 | <span data-ttu-id="40b49-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="40b49-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="40b49-119">Forrás</span><span class="sxs-lookup"><span data-stu-id="40b49-119">Source</span></span>                  | <span data-ttu-id="40b49-120">**Kiskereskedelem**, **Kézi szerkesztés**, **Kiskereskedelem és kézi készítés**</span><span class="sxs-lookup"><span data-stu-id="40b49-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="40b49-121">A **Kiskereskedelem** érték lehetővé teszi a csatorna navigációs hierarchiájának megjelenítését a Commerce központból a navigációs menüben.</span><span class="sxs-lookup"><span data-stu-id="40b49-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="40b49-122">A **Manuális szerkesztés** érték lehetővé teszi a statikus menüelemek válogatását.</span><span class="sxs-lookup"><span data-stu-id="40b49-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="40b49-123">A **Kiskereskedelem és a manuális szerkesztés** érték a kettő kombinációját is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="40b49-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="40b49-124">Kategóriaképek megjelenítése</span><span class="sxs-lookup"><span data-stu-id="40b49-124">Show category images</span></span> | <span data-ttu-id="40b49-125">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="40b49-125">**True** or **False**</span></span>    | <span data-ttu-id="40b49-126">Ha ez a tulajdonság engedélyezve van, megjeleníti a kategóriaképeket a navigációs menüben, ahogy az definiálva van a Commerce központban az egyes kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="40b49-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="40b49-127">Hozzáadva a Commerce 10.0.14-es kiadásában.</span><span class="sxs-lookup"><span data-stu-id="40b49-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="40b49-128">Többszintű navigációs menü engedélyezése</span><span class="sxs-lookup"><span data-stu-id="40b49-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="40b49-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="40b49-129">**True** or **False**</span></span> | <span data-ttu-id="40b49-130">Ha ezt a tulajdonságot engedélyezi, a navigációs menü több szinten is megjelenítheti a navigációs hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="40b49-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="40b49-131">Ez a funkció a Dynamics 365 Commerce 10.0.15 kiadásban elérhető.</span><span class="sxs-lookup"><span data-stu-id="40b49-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="40b49-132">Szintek száma</span><span class="sxs-lookup"><span data-stu-id="40b49-132">Number of levels</span></span> | <span data-ttu-id="40b49-133">egész szám</span><span class="sxs-lookup"><span data-stu-id="40b49-133">integer</span></span> | <span data-ttu-id="40b49-134">Ez a tulajdonság határozza meg a szintek számát, amelyeket meg kell jeleníteni, ha a **Többszintű navigációs menü engedélyezése** tulajdonság értéke **Igaz**.</span><span class="sxs-lookup"><span data-stu-id="40b49-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="40b49-135">Statikus menüelem</span><span class="sxs-lookup"><span data-stu-id="40b49-135">Static menu item</span></span>| <span data-ttu-id="40b49-136">Értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="40b49-136">Array of values</span></span>| <span data-ttu-id="40b49-137">A statikus menüelemek menüelemek nevét társítják egy statikus webhely-lapra mutató hivatkozással.</span><span class="sxs-lookup"><span data-stu-id="40b49-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="40b49-138">A menüelemek más menüelemek alatt is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="40b49-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="40b49-139">Alapértelmezés szerint a statikus menük a gyökér szintjén jelennek meg, és a csatorna navigációs hierarchiához lesznek hozzáfűzve, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="40b49-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="40b49-140">Gyökérmenü megjelenítése</span><span class="sxs-lookup"><span data-stu-id="40b49-140">Show root menu</span></span> | <span data-ttu-id="40b49-141">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="40b49-141">**True** or **False**</span></span> | <span data-ttu-id="40b49-142">Ha ezt a tulajdonságot engedélyezte, a navigációs menü definiálható egy egyéni gyökér (például a **Vásárlás most**) alapján is.</span><span class="sxs-lookup"><span data-stu-id="40b49-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now**).</span></span> <span data-ttu-id="40b49-143">Ez a funkció a Dynamics 365 Commerce 10.0.15 kiadásban elérhető.</span><span class="sxs-lookup"><span data-stu-id="40b49-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="40b49-144">Gyökérmenü</span><span class="sxs-lookup"><span data-stu-id="40b49-144">Root menu</span></span> | <span data-ttu-id="40b49-145">karakterlánc</span><span class="sxs-lookup"><span data-stu-id="40b49-145">string</span></span> | <span data-ttu-id="40b49-146">Ez a tulajdonság használható egy egyéni gyökér szövegének meghatározására, ha a **Gyökérmenü megjelenítése** tulajdonság értéke **Igaz**.</span><span class="sxs-lookup"><span data-stu-id="40b49-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="40b49-147">A következő ábra egy példát mutat be egy kategóriakép megjelenítésére a Fabrikam webhely navigációs menüjében.</span><span class="sxs-lookup"><span data-stu-id="40b49-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="40b49-148">![Példa egy navigációs menü moduljára a kategóriaképekkel](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="40b49-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="40b49-149">Navigációs menümodul hozzáadása a fejléc modulhoz</span><span class="sxs-lookup"><span data-stu-id="40b49-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="40b49-150">A navigációs menü modulnak a fejléc-modulba való felvételével kapcsolatos részleteket lásd a [Fejléc modul](author-header-module.md) részben.</span><span class="sxs-lookup"><span data-stu-id="40b49-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40b49-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="40b49-151">Additional resources</span></span>

[<span data-ttu-id="40b49-152">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="40b49-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="40b49-153">Útkövetési modul</span><span class="sxs-lookup"><span data-stu-id="40b49-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="40b49-154">Oldalválasztó modul</span><span class="sxs-lookup"><span data-stu-id="40b49-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="40b49-155">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="40b49-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="40b49-156">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="40b49-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="40b49-157">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="40b49-157">Header module</span></span>](author-header-module.md)
