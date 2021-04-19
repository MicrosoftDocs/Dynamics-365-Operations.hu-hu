---
title: Oldaltartalom hozzáférhetőségének ellenőrzése
description: Ez a témakör leírja, hogyan ellenőrizhető a Microsoft Dynamics 365 Commerce oldaltartalmának hozzáférhetősége.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 885696c13b0e5353e6dbd9dc21cf075d5e301786
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791631"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="82527-103">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="82527-103">Verify page content accessibility</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="82527-104">Ez a témakör leírja, hogyan ellenőrizhető a Microsoft Dynamics 365 Commerce oldaltartalmának hozzáférhetősége.</span><span class="sxs-lookup"><span data-stu-id="82527-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="82527-105">Amikor befejezte egy oldal módosítását, győződjön meg arról, hogy a tartalom mindenki számára elérhető a weben.</span><span class="sxs-lookup"><span data-stu-id="82527-105">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="82527-106">A Commerce szerkesztőeszközök könnyen ellenőrizhető az oldal tartalmának hozzáférhetősége az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatás használatával.</span><span class="sxs-lookup"><span data-stu-id="82527-106">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="82527-107">Ez a szolgáltatás ellenőrzi az oldal tartalmát a legfrissebb [World Wide Web CONSORTIUM (W3C) akadálymentesítési](https://www.w3.org/standards/webdesign/accessibility) irányelvei alapján.</span><span class="sxs-lookup"><span data-stu-id="82527-107">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="82527-108">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integrálásának használatához be kell azt kapcsolni a bérlő vagy a webhely szintjén.</span><span class="sxs-lookup"><span data-stu-id="82527-108">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="82527-109">A Microsoft hozzáférhetőségi információk bekapcsolása a bérlő összes webhelyén</span><span class="sxs-lookup"><span data-stu-id="82527-109">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="82527-110">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a bérlő összes Commerce-webhelyén, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="82527-110">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="82527-111">A bérlői beállítások eléréséhez be kell jelentkeznie a Commerce alkalmazásba rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="82527-111">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="82527-112">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="82527-112">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="82527-113">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="82527-113">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="82527-114">A **Bérlői beállítások** részben válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82527-114">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="82527-115">Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="82527-115">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="82527-116">A Microsoft hozzáférhetőségi információk bekapcsolása egyetlen webhelyhez</span><span class="sxs-lookup"><span data-stu-id="82527-116">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="82527-117">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a egyetlen Commerce-webhelyen, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="82527-117">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="82527-118">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82527-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="82527-119">A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="82527-119">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="82527-120">A **Webhelybeállítások** részben válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82527-120">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="82527-121">Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="82527-121">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="82527-122">A kezdőlapon lévő tartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="82527-122">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="82527-123">Ha az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatást szeretné használni a Commerce kezdőlapja tartalmának ellenőrzéséhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="82527-123">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="82527-124">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82527-124">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="82527-125">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82527-125">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="82527-126">Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="82527-126">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="82527-127">Válassza a parancssáv **Hozzáférhetőség ellenőrzése** elemét.</span><span class="sxs-lookup"><span data-stu-id="82527-127">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="82527-128">Megjelenik a **Hozzáférhetőség ellenőrzése** oldal.</span><span class="sxs-lookup"><span data-stu-id="82527-128">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="82527-129">A vizsgálat befejezését követően tekintse át a jelentés tartalmát.</span><span class="sxs-lookup"><span data-stu-id="82527-129">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="82527-130">Ha valamelyik ellenőrzés sikertelen, jelölje ki az egyes sikertelen elemeket a kibontáshoz, így további részleteket is meg tud tekinteni.</span><span class="sxs-lookup"><span data-stu-id="82527-130">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="82527-131">Ha az áttekintést követően be szeretné zárni a jelentést, görgessen a **Hozzáférhetőség ellenőrzése** oldal aljára, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="82527-131">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82527-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="82527-132">Additional resources</span></span>

[<span data-ttu-id="82527-133">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="82527-133">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="82527-134">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="82527-134">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="82527-135">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="82527-135">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="82527-136">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="82527-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="82527-137">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="82527-137">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="82527-138">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="82527-138">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="82527-139">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="82527-139">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="82527-140">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="82527-140">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
