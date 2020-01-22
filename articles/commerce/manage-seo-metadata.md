---
title: SEO-metaadatok kezelése
description: Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.
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
ms.openlocfilehash: 3ea06713af69659c205686a971393892fa584072
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945720"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="d2354-103">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="d2354-103">Manage SEO metadata</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d2354-104">Ez a témakör azt mutatja be, hogyan lehet kezelni a keresőmotor-optimalizálási (SEO) metaadatokat a Microsoft Dynamics 365 Commerce megoldásban.</span><span class="sxs-lookup"><span data-stu-id="d2354-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d2354-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d2354-105">Overview</span></span>

<span data-ttu-id="d2354-106">A webhely SEO metaadatait a webhelytérképek és az oldalak metaadatai használatával lehet kezelni.</span><span class="sxs-lookup"><span data-stu-id="d2354-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="d2354-107">Oldaltérképek</span><span class="sxs-lookup"><span data-stu-id="d2354-107">Site maps</span></span>

<span data-ttu-id="d2354-108">A Oldaltérkép egy géppel olvasható lista, amely XML-formátumban, a webhely oldalain található.</span><span class="sxs-lookup"><span data-stu-id="d2354-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="d2354-109">A keresőmotorok számára készült, hogy a webhelyhez jobb keresési eredményeket jelenítsenek meg.</span><span class="sxs-lookup"><span data-stu-id="d2354-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="d2354-110">Az oldaltérképeket manuálisan át lehet adni a keresőmotorok számára, vagy közzétehetők egy robots.txt fájlban.</span><span class="sxs-lookup"><span data-stu-id="d2354-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="d2354-111">A Dynamics 365 Commerce támohtaj au oldaltérképek automatikus generálását.</span><span class="sxs-lookup"><span data-stu-id="d2354-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="d2354-112">A program automatikusan frissíti az oldaltérképeket a lapok közzétételekor és közzétételük megszűntetésekor.</span><span class="sxs-lookup"><span data-stu-id="d2354-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="d2354-113">A Oldaltérkép-generálás bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="d2354-113">Turn on site map generation</span></span>

1. <span data-ttu-id="d2354-114">Jelentkezzen be a szerkesztőeszközbe.</span><span class="sxs-lookup"><span data-stu-id="d2354-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="d2354-115">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="d2354-116">A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="d2354-117">Győződjön meg arról, hogy az **Oldaltérképek engedélyezve** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="d2354-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="d2354-118">Oldal metaadatai</span><span class="sxs-lookup"><span data-stu-id="d2354-118">Page metadata</span></span>

<span data-ttu-id="d2354-119">Dynamics 365 Commerce a SEO-metaadatok kezelését lehetővé teszi az egyes oldalakhoz.</span><span class="sxs-lookup"><span data-stu-id="d2354-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="d2354-120">Ezt az információt a lap egy tárolójának **SEO-tulajdonságok** szakaszában tekintheti meg és módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="d2354-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="d2354-121">Jelenleg a következő SEO-metaadat-tulajdonságok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="d2354-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="d2354-122">Beosztás</span><span class="sxs-lookup"><span data-stu-id="d2354-122">Title</span></span>
- <span data-ttu-id="d2354-123">Leírás</span><span class="sxs-lookup"><span data-stu-id="d2354-123">Description</span></span>
- <span data-ttu-id="d2354-124">SEO-kulcsszavak</span><span class="sxs-lookup"><span data-stu-id="d2354-124">SEO keywords</span></span>
- <span data-ttu-id="d2354-125">Aria-címkék</span><span class="sxs-lookup"><span data-stu-id="d2354-125">Aria labels</span></span>
- <span data-ttu-id="d2354-126">noindex</span><span class="sxs-lookup"><span data-stu-id="d2354-126">noindex</span></span>
- <span data-ttu-id="d2354-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="d2354-127">nofollow</span></span>
- <span data-ttu-id="d2354-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="d2354-128">noarchive</span></span>
- <span data-ttu-id="d2354-129">nocache</span><span class="sxs-lookup"><span data-stu-id="d2354-129">nocache</span></span>
- <span data-ttu-id="d2354-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="d2354-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="d2354-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="d2354-131">nosnippet</span></span>
- <span data-ttu-id="d2354-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="d2354-132">noImageIndex</span></span>
- <span data-ttu-id="d2354-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="d2354-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="d2354-134">Oldal metaadatainak módosítása</span><span class="sxs-lookup"><span data-stu-id="d2354-134">Modify page metadata</span></span>

<span data-ttu-id="d2354-135">Az oldal metaadatainak módosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d2354-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="d2354-136">A **Webhelyek** alatt válassza a **Gyár** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="d2354-137">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="d2354-138">Válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="d2354-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="d2354-139">A Műveleti ablaktáblán válassza ki a **Kivétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-139">On the Action Pane, select **Check Out**.</span></span>
1. <span data-ttu-id="d2354-140">A jobb oldali tulajdonságok ablaktáblán bontsa ki az **Alapértelmezett metacímkék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="d2354-141">Új metacímke hozzáadásához kattintson a **Hozzáadás**gombra, majd írja be a címkét a mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d2354-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span>

    <span data-ttu-id="d2354-142">Ha törölni szeretne egy létező metacímkét, válassza a mellette, jobbra található kuka szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="d2354-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>

1. <span data-ttu-id="d2354-143">Válassza a **Mentés** parancsot, majd válassza a **Beadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="d2354-143">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="d2354-144">A **Megjegyzések** mezőbe írja be a **Frissített metacímkék** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d2354-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="d2354-145">A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="d2354-146">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="d2354-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="d2354-147">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2354-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2354-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d2354-148">Additional resources</span></span>

[<span data-ttu-id="d2354-149">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="d2354-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="d2354-150">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d2354-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="d2354-151">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="d2354-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="d2354-152">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="d2354-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="d2354-153">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="d2354-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="d2354-154">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="d2354-154">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="d2354-155">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="d2354-155">Verify page content accessibility</span></span>](verify-accessibility.md)
