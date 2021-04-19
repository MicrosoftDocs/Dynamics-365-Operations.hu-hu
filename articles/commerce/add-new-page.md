---
title: Új webhelyoldal hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 4a2ecc3ef3ff3f708cec50e42777b50ec4576e25
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797551"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="9c526-103">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9c526-103">Add a new site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9c526-104">Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9c526-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9c526-105">Miután létrehozott sablonokat és töredékeket a webhelyhez, a következő lépés az, hogy megkezdi az azokat használó oldalak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="9c526-105">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="9c526-106">A kezdéshez ki kell választania egy sablont vagy egy elrendezést, egy oldalnevet és egy oldal URL-t.</span><span class="sxs-lookup"><span data-stu-id="9c526-106">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="9c526-107">Sablon vagy elrendezés</span><span class="sxs-lookup"><span data-stu-id="9c526-107">Template or layout</span></span>

<span data-ttu-id="9c526-108">Az új oldalhoz egy sablon vagy egy elrendezés használható.</span><span class="sxs-lookup"><span data-stu-id="9c526-108">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="9c526-109">A további tudnivalókat lásd: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c526-109">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="9c526-110">Oldal neve</span><span class="sxs-lookup"><span data-stu-id="9c526-110">Page name</span></span>

<span data-ttu-id="9c526-111">Az oldal nevének egyedinek kell lennie az oldalon.</span><span class="sxs-lookup"><span data-stu-id="9c526-111">The page name must be unique to your page.</span></span> <span data-ttu-id="9c526-112">Leírónak kell lennie, hogy könnyen megtalálja azt, és mások tudják, hogy mire szánták a lapot.</span><span class="sxs-lookup"><span data-stu-id="9c526-112">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="9c526-113">Gondosan válassza ki a lap nevét, mert a későbbiekben nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="9c526-113">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="9c526-114">Oldal URL-címe</span><span class="sxs-lookup"><span data-stu-id="9c526-114">Page URL</span></span>

<span data-ttu-id="9c526-115">Lehetőség van az új oldal URL-címének megadására is.</span><span class="sxs-lookup"><span data-stu-id="9c526-115">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="9c526-116">Az oldalak létrehozásakor megadhatja a teljes URL-cím alapjául szolgáló karakterláncot.</span><span class="sxs-lookup"><span data-stu-id="9c526-116">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="9c526-117">Ez a karaktersorozat ismert relatív URL vagy URL alkategória néven is.</span><span class="sxs-lookup"><span data-stu-id="9c526-117">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="9c526-118">A program ezt követően egy teljes URL-címet generál, és az új oldalt hozzárendeli a program az URL alkategória alapján.</span><span class="sxs-lookup"><span data-stu-id="9c526-118">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="9c526-119">Később a lap közzététele előtt módosíthatja az URL alkategóriát.</span><span class="sxs-lookup"><span data-stu-id="9c526-119">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="9c526-120">További tudnivalókkal kapcsolatban lásd: [Weblap URL-címének létrehozása](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="9c526-120">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9c526-121">A Dynamics 365 Commerce leválasztja az URL-címeket és a tartalmat.</span><span class="sxs-lookup"><span data-stu-id="9c526-121">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="9c526-122">Más szóval egy olyan oldalt is létre lehet hozni, amely nem URL-címhez van társítva, és létre lehet hozni egy URL-címet, amely nincs egy oldalhoz társítva.</span><span class="sxs-lookup"><span data-stu-id="9c526-122">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="9c526-123">Ezért a tartalomcsere végrehajtható egy URL esetében, és nem igényel állásidőt, valamint az átirányítások könnyebben kezelhetők.</span><span class="sxs-lookup"><span data-stu-id="9c526-123">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="9c526-124">Új oldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9c526-124">Add a new page</span></span>

<span data-ttu-id="9c526-125">Ha új webhelyoldalt szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9c526-125">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="9c526-126">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-126">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9c526-127">Válassza az **Új oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-127">Select **New Page**.</span></span>
1. <span data-ttu-id="9c526-128">Az **Új oldal** párbeszédpanelen válasszon ki egy sablont, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9c526-128">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="9c526-129">Az **Oldal neve** mezőben adjon meg egy nevet (például **Az új oldalam**).</span><span class="sxs-lookup"><span data-stu-id="9c526-129">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="9c526-130">Az **URL** mezőbe írja be az URL kiegészítésére szolgáló karaktersorozatot (URL alkategória) (például **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="9c526-130">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="9c526-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-131">Select **OK**.</span></span> <span data-ttu-id="9c526-132">Megjelenik az oldalszerkesztő.</span><span class="sxs-lookup"><span data-stu-id="9c526-132">The page editor appears.</span></span> <span data-ttu-id="9c526-133">Figyelje meg, hogy a kiválasztott sablon alapján a program automatikusan hozzáadja a fejlécet és a láblécet az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="9c526-133">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="9c526-134">Az oldalstruktúrában válassza ki a **Fő** helyet, válassza ki a három pontot (**…**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9c526-134">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9c526-135">Válassza a **Tároló**, majd az **OK** elemet</span><span class="sxs-lookup"><span data-stu-id="9c526-135">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="9c526-136">Válassza ki a **Folyékony tároló** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9c526-136">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9c526-137">Válassza ki a **Tartalomgazdag blokk** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9c526-137">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c526-138">Válassza ki a **Tartalomgazdag blokk** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9c526-138">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9c526-139">Válassza ki a **Tartalomgazdag blokk elem** lehetőséget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9c526-139">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c526-140">A jobb oldali tulajdonságok panelen válassza a **Bekezdés** elemet, majd a mezőbe írja be **Saját tesztszöveg** szöveget.</span><span class="sxs-lookup"><span data-stu-id="9c526-140">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="9c526-141">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="9c526-141">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="9c526-142">A **Megjegyzések** mezőbe írja be az **Új oldal hozzáadva** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9c526-142">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c526-143">A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-143">Select **Preview** to preview your page.</span></span> <span data-ttu-id="9c526-144">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="9c526-144">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="9c526-145">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-145">Select **Publish**.</span></span>
1. <span data-ttu-id="9c526-146">A navigációs útvonalon (navigációs eszközök) válassza ki a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-146">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9c526-147">A bal oldali navigációs ablakban válassza ki az **URL-címek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-147">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="9c526-148">Keresse meg és válassza ki az URL-címét (**mynewpage**) a listából.</span><span class="sxs-lookup"><span data-stu-id="9c526-148">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="9c526-149">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c526-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c526-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9c526-150">Additional resources</span></span>

[<span data-ttu-id="9c526-151">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="9c526-151">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="9c526-152">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="9c526-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="9c526-153">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="9c526-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="9c526-154">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="9c526-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="9c526-155">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="9c526-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="9c526-156">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="9c526-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="9c526-157">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="9c526-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="9c526-158">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="9c526-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
