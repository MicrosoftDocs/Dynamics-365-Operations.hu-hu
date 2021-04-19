---
title: SEO-metaadatok kezelése
description: Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.
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
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794211"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="3b132-103">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="3b132-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3b132-104">Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.</span><span class="sxs-lookup"><span data-stu-id="3b132-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3b132-105">A webhely SEO metaadatait a webhelytérképek és az oldalak metaadatai használatával lehet kezelni.</span><span class="sxs-lookup"><span data-stu-id="3b132-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="3b132-106">Oldaltérképek</span><span class="sxs-lookup"><span data-stu-id="3b132-106">Site maps</span></span>

<span data-ttu-id="3b132-107">A Oldaltérkép egy géppel olvasható lista, amely XML-formátumban, a webhely oldalain található.</span><span class="sxs-lookup"><span data-stu-id="3b132-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="3b132-108">A keresőmotorok számára készült, hogy a webhelyhez jobb keresési eredményeket jelenítsenek meg.</span><span class="sxs-lookup"><span data-stu-id="3b132-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="3b132-109">Az oldaltérképeket manuálisan át lehet adni a keresőmotorok számára, vagy közzétehetők egy robots.txt fájlban.</span><span class="sxs-lookup"><span data-stu-id="3b132-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="3b132-110">A Dynamics 365 Commerce támohtaj au oldaltérképek automatikus generálását.</span><span class="sxs-lookup"><span data-stu-id="3b132-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="3b132-111">A program automatikusan frissíti az oldaltérképeket a lapok közzétételekor és közzétételük megszűntetésekor.</span><span class="sxs-lookup"><span data-stu-id="3b132-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="3b132-112">A Oldaltérkép-generálás bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="3b132-112">Turn on site map generation</span></span>

1. <span data-ttu-id="3b132-113">Jelentkezzen be a szerkesztőeszközbe.</span><span class="sxs-lookup"><span data-stu-id="3b132-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="3b132-114">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="3b132-115">A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="3b132-116">Győződjön meg arról, hogy az **Oldaltérképek engedélyezve** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="3b132-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="3b132-117">Oldal metaadatai</span><span class="sxs-lookup"><span data-stu-id="3b132-117">Page metadata</span></span>

<span data-ttu-id="3b132-118">Dynamics 365 Commerce a SEO-metaadatok kezelését lehetővé teszi az egyes oldalakhoz.</span><span class="sxs-lookup"><span data-stu-id="3b132-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="3b132-119">Ezt az információt a lap egy tárolójának **SEO-tulajdonságok** szakaszában tekintheti meg és módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="3b132-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="3b132-120">Jelenleg a következő SEO-metaadat-tulajdonságok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="3b132-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="3b132-121">Beosztás</span><span class="sxs-lookup"><span data-stu-id="3b132-121">Title</span></span>
- <span data-ttu-id="3b132-122">Leírás</span><span class="sxs-lookup"><span data-stu-id="3b132-122">Description</span></span>
- <span data-ttu-id="3b132-123">SEO-kulcsszavak</span><span class="sxs-lookup"><span data-stu-id="3b132-123">SEO keywords</span></span>
- <span data-ttu-id="3b132-124">Aria-címkék</span><span class="sxs-lookup"><span data-stu-id="3b132-124">Aria labels</span></span>
- <span data-ttu-id="3b132-125">noindex</span><span class="sxs-lookup"><span data-stu-id="3b132-125">noindex</span></span>
- <span data-ttu-id="3b132-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="3b132-126">nofollow</span></span>
- <span data-ttu-id="3b132-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="3b132-127">noarchive</span></span>
- <span data-ttu-id="3b132-128">nocache</span><span class="sxs-lookup"><span data-stu-id="3b132-128">nocache</span></span>
- <span data-ttu-id="3b132-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="3b132-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="3b132-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="3b132-130">nosnippet</span></span>
- <span data-ttu-id="3b132-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="3b132-131">noImageIndex</span></span>
- <span data-ttu-id="3b132-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="3b132-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="3b132-133">Oldal metaadatainak módosítása</span><span class="sxs-lookup"><span data-stu-id="3b132-133">Modify page metadata</span></span>

<span data-ttu-id="3b132-134">Az oldal metaadatainak módosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3b132-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="3b132-135">A **Webhelyek** alatt válassza a **Gyár** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="3b132-136">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="3b132-137">Válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="3b132-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="3b132-138">Válassza a parancssáv **Szerkesztés** elemét.</span><span class="sxs-lookup"><span data-stu-id="3b132-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="3b132-139">A jobb oldali tulajdonságok ablaktáblán bontsa ki az **Alapértelmezett metacímkék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="3b132-140">Új metacímke hozzáadásához kattintson a **Hozzáadás** gombra, majd írja be a címkét a mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3b132-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="3b132-141">Ha törölni szeretne egy létező metacímkét, válassza a mellette, jobbra található kuka szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="3b132-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="3b132-142">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="3b132-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3b132-143">A **Megjegyzések** mezőbe írja be a **Frissített metacímkék** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3b132-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="3b132-144">A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="3b132-145">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="3b132-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="3b132-146">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b132-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3b132-147">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3b132-147">Additional resources</span></span>

[<span data-ttu-id="3b132-148">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="3b132-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="3b132-149">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="3b132-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="3b132-150">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="3b132-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="3b132-151">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="3b132-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="3b132-152">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="3b132-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="3b132-153">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="3b132-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="3b132-154">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="3b132-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="3b132-155">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="3b132-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
