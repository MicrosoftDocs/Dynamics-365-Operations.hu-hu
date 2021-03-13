---
title: Gyorsnézeti modul
description: Ez a témakör a gyorsnézeti modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 7e8244a06c515029b559b2061d9a25c7355e9e14
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097052"
---
# <a name="quick-view-module"></a><span data-ttu-id="d0c74-103">Gyorsnézeti modul</span><span class="sxs-lookup"><span data-stu-id="d0c74-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="d0c74-104">Ez a témakör a gyorsnézeti modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d0c74-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d0c74-105">A gyorsnézeti modul segítségével a felhasználók gyorsan megtekinthetik a termékinformációkat, amikor a termékeket egy listaoldalon böngészik, és egy vagy több terméket adnak a kosárhoz a listaoldalról anélkül, hogy a termék részleteit tartalmazó oldalra (PDP) kellene lépniük.</span><span class="sxs-lookup"><span data-stu-id="d0c74-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="d0c74-106">A gyorsnézeti modul áttekintést nyújt a felhasználók által a „hozzáadás a kosárhoz” döntés meghozatalához szükséges termékinformációkról.</span><span class="sxs-lookup"><span data-stu-id="d0c74-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="d0c74-107">A PDP-re mutató hivatkozást is tartalmaz, így a felhasználók további termékrészleteket és vásárlási lehetőségeket tekinthetnek meg.</span><span class="sxs-lookup"><span data-stu-id="d0c74-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="d0c74-108">A gyorsnézeti modult a [termékgyűjtési](product-collection-module-overview.md) és a [keresési eredmények](search-result-module.md) modul támogatja.</span><span class="sxs-lookup"><span data-stu-id="d0c74-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0c74-109">A gyorsnézeti modul a Commerce 10.0.17-es verziójának kiadásaként érhető el.</span><span class="sxs-lookup"><span data-stu-id="d0c74-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="d0c74-110">A következő ábra bemutat egy példát egy gyorsnézeti modulról egy terméklistaoldalon.</span><span class="sxs-lookup"><span data-stu-id="d0c74-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Példa gyorsnézeti modulra egy terméklistaoldalon](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="d0c74-112">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="d0c74-112">Module properties</span></span>

<span data-ttu-id="d0c74-113">A gyorsnézeti modul ugyanazokat a funkciókat támogatja, mint a vásárlásmező modul.</span><span class="sxs-lookup"><span data-stu-id="d0c74-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="d0c74-114">Ezért a gyorsnézeti modul tulajdonságai hasonlítanak a vásárlásmező modul tulajdonságaira.</span><span class="sxs-lookup"><span data-stu-id="d0c74-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="d0c74-115">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="d0c74-115">Property</span></span> | <span data-ttu-id="d0c74-116">Értékek</span><span class="sxs-lookup"><span data-stu-id="d0c74-116">Values</span></span> | <span data-ttu-id="d0c74-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="d0c74-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="d0c74-118">Címsor címkéje</span><span class="sxs-lookup"><span data-stu-id="d0c74-118">Heading tag</span></span> | <span data-ttu-id="d0c74-119">**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**</span><span class="sxs-lookup"><span data-stu-id="d0c74-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="d0c74-120">Ez a tulajdonság határozza meg a termék címének címsorcímkéjét.</span><span class="sxs-lookup"><span data-stu-id="d0c74-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="d0c74-121">Ha a gyornézeti modul a lap felső részén van, a tulajdonságot a **H1** értékre kell állítania a hozzáférhetőségi szabványok teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="d0c74-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="d0c74-122">Egyéni ár engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d0c74-122">Allow custom price</span></span> | <span data-ttu-id="d0c74-123">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="d0c74-123">**True** or **False**</span></span> | <span data-ttu-id="d0c74-124">Ha a tulajdonság értéke **Igaz**, a felhasználó egyéni árat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="d0c74-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="d0c74-125">Minimális ár</span><span class="sxs-lookup"><span data-stu-id="d0c74-125">Minimum price</span></span> | <span data-ttu-id="d0c74-126">Egész</span><span class="sxs-lookup"><span data-stu-id="d0c74-126">Integer</span></span> | <span data-ttu-id="d0c74-127">Ez a tulajdonság csak akkor alkalmazható, ha az **Egyéni ár engedélyezése** tulajdonság értéke **Igaz**.</span><span class="sxs-lookup"><span data-stu-id="d0c74-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="d0c74-128">Meghatározza a felhasználó által beírható minimális árat (például 1 dollár).</span><span class="sxs-lookup"><span data-stu-id="d0c74-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="d0c74-129">Maximális ár</span><span class="sxs-lookup"><span data-stu-id="d0c74-129">Maximum price</span></span> | <span data-ttu-id="d0c74-130">Egész</span><span class="sxs-lookup"><span data-stu-id="d0c74-130">Integer</span></span> | <span data-ttu-id="d0c74-131">Ez a tulajdonság csak akkor alkalmazható, ha az **Egyéni ár engedélyezése** tulajdonság értéke **Igaz**.</span><span class="sxs-lookup"><span data-stu-id="d0c74-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="d0c74-132">Meghatározza a felhasználó által beírható maximális árat (például 1000 dollár).</span><span class="sxs-lookup"><span data-stu-id="d0c74-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="d0c74-133">Commerce webhelykészítő beállításai</span><span class="sxs-lookup"><span data-stu-id="d0c74-133">Commerce site builder settings</span></span>

<span data-ttu-id="d0c74-134">A vásárlásmező modulhoz hasonlóan a gyorsnézeti modul is tiszteletben tartja a **Webhelybeállítások \> Bővítmények \> Termék hozzáadása a kosárhoz** beállításait.</span><span class="sxs-lookup"><span data-stu-id="d0c74-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="d0c74-135">Azonban a **Navigálás a kosárhoz oldal** beállítást figyelmen kívül hagyja, mivel az nem egyeztethető össze a gyorsnézeti modul céljával, amely lehetővé teszi a felhasználók számára, hogy több terméket böngésszenek egy listoldalon, és a listaoldal elhagyása nélkül hozzáadják őket a kosárhoz.</span><span class="sxs-lookup"><span data-stu-id="d0c74-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="d0c74-136">Gyornézeti modul hozzáadása termékgyűjtési modulhoz</span><span class="sxs-lookup"><span data-stu-id="d0c74-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="d0c74-137">A gyorsnézeti modult hozzáadhatja a termékgyűjtési és a keresési eredmények modulhoz.</span><span class="sxs-lookup"><span data-stu-id="d0c74-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="d0c74-138">A gyorsnézeti modulnak a termékgyűjtési modulhoz való hozzáadásához a a Commerce webhelykészítő felületén hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d0c74-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d0c74-139">Nyissa meg az **Oldalak** lehetőséget, majd válassza ki a Fabrikam webhely kezdőlapját.</span><span class="sxs-lookup"><span data-stu-id="d0c74-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="d0c74-140">Lépjen a kezdőlap bármelyik **Termékgyűjtemény** moduljára, jelölje ki a három pontot (**...**), majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c74-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d0c74-141">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Gyorsnézet** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d0c74-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d0c74-142">A **Gyorsnézet** modul tulajdonságok paneljében válassza a **Címsor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c74-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="d0c74-143">A **Címsor** párbeszédpanelen állítsa a **Címsor szintje** mezőt **H2** értékre, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d0c74-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="d0c74-144">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="d0c74-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0c74-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d0c74-145">Additional resources</span></span>

[<span data-ttu-id="d0c74-146">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="d0c74-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d0c74-147">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="d0c74-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d0c74-148">Termékgyűjtési modul</span><span class="sxs-lookup"><span data-stu-id="d0c74-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="d0c74-149">Keresési eredmények modul</span><span class="sxs-lookup"><span data-stu-id="d0c74-149">Search results module</span></span>](search-result-module.md)
