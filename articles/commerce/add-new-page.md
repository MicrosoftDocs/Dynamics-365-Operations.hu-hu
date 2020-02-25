---
title: Új webhelyoldal hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 68461f1f0be46f979a67e1806e03c02200cf61db
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001346"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="89592-103">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89592-103">Add a new site page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="89592-104">Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="89592-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="89592-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="89592-105">Overview</span></span>

<span data-ttu-id="89592-106">Miután létrehozott sablonokat és töredékeket a webhelyhez, a következő lépés az, hogy megkezdi az azokat használó oldalak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="89592-106">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="89592-107">A kezdéshez ki kell választania egy sablont vagy egy elrendezést, egy oldalnevet és egy oldal URL-t.</span><span class="sxs-lookup"><span data-stu-id="89592-107">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="89592-108">Sablon vagy elrendezés</span><span class="sxs-lookup"><span data-stu-id="89592-108">Template or layout</span></span>

<span data-ttu-id="89592-109">Az új oldalhoz egy sablon vagy egy elrendezés használható.</span><span class="sxs-lookup"><span data-stu-id="89592-109">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="89592-110">A további tudnivalókat lásd: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="89592-110">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="89592-111">Oldal neve</span><span class="sxs-lookup"><span data-stu-id="89592-111">Page name</span></span>

<span data-ttu-id="89592-112">Az oldal nevének egyedinek kell lennie az oldalon.</span><span class="sxs-lookup"><span data-stu-id="89592-112">The page name must be unique to your page.</span></span> <span data-ttu-id="89592-113">Leírónak kell lennie, hogy könnyen megtalálja azt, és mások tudják, hogy mire szánták a lapot.</span><span class="sxs-lookup"><span data-stu-id="89592-113">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="89592-114">Gondosan válassza ki a lap nevét, mert a későbbiekben nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="89592-114">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="89592-115">Oldal URL-címe</span><span class="sxs-lookup"><span data-stu-id="89592-115">Page URL</span></span>

<span data-ttu-id="89592-116">Lehetőség van az új oldal URL-címének megadására is.</span><span class="sxs-lookup"><span data-stu-id="89592-116">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="89592-117">Az oldalak létrehozásakor megadhatja a teljes URL-cím alapjául szolgáló karakterláncot.</span><span class="sxs-lookup"><span data-stu-id="89592-117">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="89592-118">Ez a karaktersorozat ismert relatív URL vagy URL alkategória néven is.</span><span class="sxs-lookup"><span data-stu-id="89592-118">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="89592-119">A program ezt követően egy teljes URL-címet generál, és az új oldalt hozzárendeli a program az URL alkategória alapján.</span><span class="sxs-lookup"><span data-stu-id="89592-119">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="89592-120">Később a lap közzététele előtt módosíthatja az URL alkategóriát.</span><span class="sxs-lookup"><span data-stu-id="89592-120">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="89592-121">További tudnivalókkal kapcsolatban lásd: [Weblap URL-címének létrehozása](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="89592-121">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89592-122">A Dynamics 365 Commerce leválasztja az URL-címeket és a tartalmat.</span><span class="sxs-lookup"><span data-stu-id="89592-122">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="89592-123">Más szóval egy olyan oldalt is létre lehet hozni, amely nem URL-címhez van társítva, és létre lehet hozni egy URL-címet, amely nincs egy oldalhoz társítva.</span><span class="sxs-lookup"><span data-stu-id="89592-123">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="89592-124">Ezért a tartalomcsere végrehajtható egy URL esetében, és nem igényel állásidőt, valamint az átirányítások könnyebben kezelhetők.</span><span class="sxs-lookup"><span data-stu-id="89592-124">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="89592-125">Új oldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89592-125">Add a new page</span></span>

<span data-ttu-id="89592-126">Ha új webhelyoldalt szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="89592-126">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="89592-127">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-127">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="89592-128">Válassza az **Új oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-128">Select **New Page**.</span></span>
1. <span data-ttu-id="89592-129">Az **Új oldal** párbeszédpanelen válasszon ki egy sablont, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="89592-129">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="89592-130">Az **Oldal neve** mezőben adjon meg egy nevet (például **Az új oldalam**).</span><span class="sxs-lookup"><span data-stu-id="89592-130">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="89592-131">Az **URL** mezőbe írja be az URL kiegészítésére szolgáló karaktersorozatot (URL alkategória) (például **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="89592-131">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="89592-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-132">Select **OK**.</span></span> <span data-ttu-id="89592-133">Megjelenik az oldalszerkesztő.</span><span class="sxs-lookup"><span data-stu-id="89592-133">The page editor appears.</span></span> <span data-ttu-id="89592-134">Figyelje meg, hogy a kiválasztott sablon alapján a program automatikusan hozzáadja a fejlécet és a láblécet az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="89592-134">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="89592-135">Az oldalstruktúrában válassza ki a **Fő** helyet, válassza ki a három pontot (**…**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="89592-135">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="89592-136">Válassza a **Tároló**, majd az **OK** elemet</span><span class="sxs-lookup"><span data-stu-id="89592-136">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="89592-137">Válassza ki a **Folyékony tároló** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="89592-137">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="89592-138">Válassza ki a **Tartalomgazdag blokk** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="89592-138">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="89592-139">Válassza ki a **Tartalomgazdag blokk** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="89592-139">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="89592-140">Válassza ki a **Tartalomgazdag blokk elem** lehetőséget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="89592-140">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="89592-141">A jobb oldali tulajdonságok panelen válassza a **Bekezdés** elemet, majd a mezőbe írja be **Saját tesztszöveg** szöveget.</span><span class="sxs-lookup"><span data-stu-id="89592-141">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="89592-142">Válassza a **Mentés** parancsot, majd válassza a **Beadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="89592-142">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="89592-143">A **Megjegyzések** mezőbe írja be az **Új oldal hozzáadva** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="89592-143">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="89592-144">A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="89592-145">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="89592-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="89592-146">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-146">Select **Publish**.</span></span>
1. <span data-ttu-id="89592-147">A navigációs útvonalon (navigációs eszközök) válassza ki a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-147">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="89592-148">A bal oldali navigációs ablakban válassza ki az **URL-címek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-148">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="89592-149">Keresse meg és válassza ki az URL-címét (**mynewpage**) a listából.</span><span class="sxs-lookup"><span data-stu-id="89592-149">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="89592-150">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89592-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89592-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="89592-151">Additional resources</span></span>

[<span data-ttu-id="89592-152">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="89592-152">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="89592-153">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="89592-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="89592-154">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="89592-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="89592-155">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="89592-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="89592-156">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="89592-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="89592-157">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="89592-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="89592-158">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="89592-158">Verify page content accessibility</span></span>](verify-accessibility.md)
