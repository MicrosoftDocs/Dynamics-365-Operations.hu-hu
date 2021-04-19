---
title: Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján
description: Ez a témakör azt mutatja be, hogyan lehet beállítani olyan Microsoft Dynamics 365 Commerce e-kereskedelmi oldalt, amely az URL-paraméterek alapján szolgáltat dinamikus tartalmat.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8f59b80880e6947e1b45c110df0e78d4bdd57c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795811"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="5e13d-103">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="5e13d-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5e13d-104">Ez a témakör azt mutatja be, hogyan lehet beállítani olyan Microsoft Dynamics 365 Commerce e-kereskedelmi oldalt, amely az URL-paraméterek alapján szolgáltat dinamikus tartalmat.</span><span class="sxs-lookup"><span data-stu-id="5e13d-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="5e13d-105">Az e-kereskedelmi oldalak különböző tartalmak nyújtására konfigurálhatók az URL elérési útjának egy szegmense alapján.</span><span class="sxs-lookup"><span data-stu-id="5e13d-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="5e13d-106">Ennek megfelelően az oldal dinamikus oldalként ismert.</span><span class="sxs-lookup"><span data-stu-id="5e13d-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="5e13d-107">A szegmenst a program paraméterként használja az oldal tartalmának beolvasására.</span><span class="sxs-lookup"><span data-stu-id="5e13d-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="5e13d-108">Létrehoznak például egy **blog\_viewer** nevű lapot, amelyet a `https://fabrikam.com/blog` URL-címhez társítanak.</span><span class="sxs-lookup"><span data-stu-id="5e13d-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="5e13d-109">Ezen a lapon különböző tartalmak láthatók az URL elérési útjának utolsó szegmense alapján.</span><span class="sxs-lookup"><span data-stu-id="5e13d-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="5e13d-110">A `https://fabrikam.com/blog/article-1` URL utolsó szegmense például: **article-1**.</span><span class="sxs-lookup"><span data-stu-id="5e13d-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="5e13d-111">Az URL elérési útjában található szegmenseihez különálló, a dinamikus oldalt felülbíráló egyéni lapok is társíthatók.</span><span class="sxs-lookup"><span data-stu-id="5e13d-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="5e13d-112">Létrehoznak például egy **blog\_summary** nevű lapot, amelyet a `https://fabrikam.com/blog/about-this-blog` URL-címhez társítanak.</span><span class="sxs-lookup"><span data-stu-id="5e13d-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="5e13d-113">Az URL lekérése esetén a rendszer az **about-this-blog** paraméterrel társított **blog\_summary** oldalt jeleníti meg a **blog\_viewer** oldal helyett.</span><span class="sxs-lookup"><span data-stu-id="5e13d-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="5e13d-114">A dinamikus oldal tartalmának tárhelyre, beolvasásra és megjelenítésre vonatkozó funkcióit egy egyéni modul használatával valósítják meg.</span><span class="sxs-lookup"><span data-stu-id="5e13d-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="5e13d-115">További információt az [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md) című témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="5e13d-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="5e13d-116">Dinamikus e-kereskedelmi oldal beállítása</span><span class="sxs-lookup"><span data-stu-id="5e13d-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="5e13d-117">Dinamikus e-kereskedelmi oldal létrehozásához létre kell hoznia egy dinamikus lapot, létre kell hoznia az alap URL-címet, majd konfigurálnia kell a dinamikus oldal útvonalát.</span><span class="sxs-lookup"><span data-stu-id="5e13d-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="5e13d-118">A dinamikus tartalmat szolgáltató oldal létrehozása</span><span class="sxs-lookup"><span data-stu-id="5e13d-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="5e13d-119">Dinamikus tartalmat szolgáltató oldal létrehozásához kövesse az [Új webhelyoldal hozzáadása](add-new-page.md) pontban leírt lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e13d-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="5e13d-120">A létrehozott oldalhoz egy olyan modul implementálására lesz szükség, amely az URL elérési útjának utolsó szegmensét használja a külső adatforrásból származó tartalom beolvasására.</span><span class="sxs-lookup"><span data-stu-id="5e13d-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="5e13d-121">Az egyéni modul fejlesztésével kapcsolatos további tudnivalókat lásd az [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md) pontban.</span><span class="sxs-lookup"><span data-stu-id="5e13d-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="5e13d-122">A dinamikus oldal alap URL-címének létrehozása</span><span class="sxs-lookup"><span data-stu-id="5e13d-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="5e13d-123">A dinamikus oldal alap URL-címének Commerce webhelykészítőben történő létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e13d-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e13d-124">Lépjen az **URL-ek** pontra, és válassza az **Új \> Új URL** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="5e13d-125">Az **Új URL-cím létrehozása** párbeszédpanelen válassza a **Belső oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="5e13d-126">Az **URL elérési útja** pontban adja meg a dinamikus lap gyökereként szolgáló elérési utat (ebben a példában: **/blog**).</span><span class="sxs-lookup"><span data-stu-id="5e13d-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="5e13d-127">Majd válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-127">Then select **Next**.</span></span>
1. <span data-ttu-id="5e13d-128">Az **Oldal kiválasztása** párbeszédpanelen válassza ki a létrehozott, dinamikus oldalként működtetni kívánt oldalt, majd kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="5e13d-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="5e13d-129">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="5e13d-130">Dinamikus oldal útvonalának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5e13d-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="5e13d-131">A dinamikus oldalra mutató útvonal Commerce webhelykészítőben történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e13d-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e13d-132">Lépjen a **Webhelybeállítások \> Bővítmények** pontra.</span><span class="sxs-lookup"><span data-stu-id="5e13d-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="5e13d-133">A **Paraméterezett URL elérési utak** mezőben válassza a **Hozzáadás** lehetőséget, majd adja meg az URL létrehozásakor megadott URL elérési utat (ebben a példában: **/blog**).</span><span class="sxs-lookup"><span data-stu-id="5e13d-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="5e13d-134">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-134">Select **Save and publish**.</span></span>

<span data-ttu-id="5e13d-135">Az útvonal konfigurálása után a paraméterezett URL elérési úthoz tartozó összes kérés az adott URL-hez társított oldalt tölti be.</span><span class="sxs-lookup"><span data-stu-id="5e13d-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="5e13d-136">Ha a kérések egy további szegmenst tartalmaznak, a társított lap megjelenik, és az oldal tartalmának beolvasása a szegmens használatával történik paraméterként.</span><span class="sxs-lookup"><span data-stu-id="5e13d-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="5e13d-137">A `https://fabrikam.com/blog/article-1` például a **blog\_summary** oldalt jeleníti meg, az oldal tartalmának betöltése pedig az **/article-1** paraméterrel történik.</span><span class="sxs-lookup"><span data-stu-id="5e13d-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="5e13d-138">Paraméterezett URL elérési út felülbírálása egyéni oldal használatával</span><span class="sxs-lookup"><span data-stu-id="5e13d-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="5e13d-139">Ha felül szeretne bírálni egy paraméterezett URL elérési utat egy egyéni oldallal a Commerce webhelykészítőben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e13d-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e13d-140">Lépjen az **URL-ek** pontra, és válassza az **Új \> Új URL** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="5e13d-141">Az **Új URL-cím létrehozása** párbeszédpanelen válassza a **Belső oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="5e13d-142">Az **URL elérési útja** pontba írja be a felülbírálni kívánt szegmenst tartalmazó elérési utat (ebben a példában: **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="5e13d-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="5e13d-143">Majd válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-143">Then select **Next**.</span></span>
1. <span data-ttu-id="5e13d-144">Az **Oldal kiválasztása** párbeszédpanelen válassza ki az egyéni oldalt, majd válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="5e13d-145">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-145">Select **Publish**.</span></span>
1. <span data-ttu-id="5e13d-146">Ha még nem tette közzé az egyéni oldalt, lépjen az **Oldalak** lehetőségre, válassza ki az egyéni oldalt, majd válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e13d-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="5e13d-147">Az egyéni oldal közzététele után a rendszer az egyéni oldalt jeleníti meg a paraméterezett tartalommal rendelkező dinamikus oldal helyett.</span><span class="sxs-lookup"><span data-stu-id="5e13d-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e13d-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5e13d-148">Additional resources</span></span>

[<span data-ttu-id="5e13d-149">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="5e13d-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="5e13d-150">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="5e13d-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="5e13d-151">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="5e13d-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="5e13d-152">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="5e13d-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="5e13d-153">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="5e13d-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="5e13d-154">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="5e13d-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="5e13d-155">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="5e13d-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="5e13d-156">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="5e13d-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="5e13d-157">Online csatorna bővíthetősége</span><span class="sxs-lookup"><span data-stu-id="5e13d-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
