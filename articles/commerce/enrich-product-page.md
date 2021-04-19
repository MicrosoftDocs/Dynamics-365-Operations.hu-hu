---
title: A termékoldal bővítése
description: Ez a témakör azt mutatja be, hogyan lehet egy bővíteni egy terméklapot a Microsoft Dynamics 365 Commerce alkalmazásban.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6c1a9474ed514426386b1d7b4a72b62129cdb8a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799044"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="45395-103">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="45395-103">Enrich a product page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="45395-104">Ez a témakör azt mutatja be, hogyan lehet egy bővíteni egy terméklapot a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="45395-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="45395-105">Alapértelmezés szerint a webhelye általános lapot használ a termék adatainak megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="45395-105">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="45395-106">Ez a lap a termékkel kapcsolatos alapadatokat és az értékesítéshez szükséges vezérlőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="45395-106">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="45395-107">A Commerce Scale Unit rendszerből származó információkat azonban egy adott termékhez tartozó további képekkel vagy szöveggel lehet kiegészíteni.</span><span class="sxs-lookup"><span data-stu-id="45395-107">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="45395-108">Ezt a folyamatot nevezzük a terméklap bővítésének.</span><span class="sxs-lookup"><span data-stu-id="45395-108">This process is known as enriching the product page.</span></span>

<span data-ttu-id="45395-109">Sok esetben előfordulhat, hogy a termékhez külön további tartalmat kíván használni.</span><span class="sxs-lookup"><span data-stu-id="45395-109">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="45395-110">Amikor a **Kiskereskedelem és kereskedelem** lehetőségre lép a szerkesztési eszközben, akkor a webhelyhez rendelt csatornából származó termékek listáját fogja látni.</span><span class="sxs-lookup"><span data-stu-id="45395-110">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="45395-111">Ebben a listában a **Bővített** oszlop jelzi, hogy az adott termékhez tartozó terméklap bővített-e.</span><span class="sxs-lookup"><span data-stu-id="45395-111">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="45395-112">Ha ebben az oszlopban pipa látható, akkor a termékhez létezik egy bővített terméklap.</span><span class="sxs-lookup"><span data-stu-id="45395-112">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="45395-113">Ha nem látható pipa, akkor a termékhez a program az alapértelmezett terméklapot és tartalmat használja.</span><span class="sxs-lookup"><span data-stu-id="45395-113">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="45395-114">A listában a termék nevére kattintva megtekintheti a bővített és nem bővített terméklapokat.</span><span class="sxs-lookup"><span data-stu-id="45395-114">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="45395-115">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="45395-115">Enrich a product page</span></span>

<span data-ttu-id="45395-116">A termék oldalának bővítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="45395-116">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="45395-117">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45395-117">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="45395-118">A bal oldali navigációs ablakban válassza ki a **Termékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45395-118">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="45395-119">Válassza ki azokat a termékeket, amelyeknél nem szerepel bővített terméklap.</span><span class="sxs-lookup"><span data-stu-id="45395-119">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="45395-120">A Művelet ablaktáblán válassza ki a **Terméklap bővítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-120">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="45395-121">Válassza a **PDP-sablon**, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-121">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="45395-122">A bal oldali oldalstruktúrán bontsa ki a **Fő** helyet.</span><span class="sxs-lookup"><span data-stu-id="45395-122">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="45395-123">Válassza ki a **Fő** helyhez tartozó három pont gombot (**...**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-123">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="45395-124">Válassza a **Tároló 2**, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-124">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="45395-125">Válassza ki a **Tárolós 2** helyhez tartozó három pont gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-125">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="45395-126">Válassza a **Funkció** parancsot, majd válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-126">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="45395-127">A jobb oldali tulajdonságok panel **Rich Text** mezőbe írja be a termék frissített leírását.</span><span class="sxs-lookup"><span data-stu-id="45395-127">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="45395-128">A **Fejléc** mezőbe írja be a fejléc szövegét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="45395-128">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="45395-129">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="45395-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="45395-130">A **Megjegyzések** mezőbe írja be a **Termék bővítve** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="45395-130">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="45395-131">A bővített terméklap előnézetéhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45395-131">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="45395-132">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="45395-132">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="45395-133">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45395-133">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45395-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45395-134">Additional resources</span></span>

[<span data-ttu-id="45395-135">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="45395-135">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="45395-136">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="45395-136">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="45395-137">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="45395-137">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="45395-138">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="45395-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="45395-139">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="45395-139">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="45395-140">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="45395-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="45395-141">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="45395-141">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="45395-142">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="45395-142">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
