---
title: Oldaltartalom hozzáférhetőségének ellenőrzése
description: Ez a témakör leírja, hogyan ellenőrizhető a Microsoft Dynamics 365 Commerce oldaltartalmának hozzáférhetősége.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fc3dca673510e1636f497bb7d5c295bebe025677
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015103"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="810d2-103">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="810d2-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="810d2-104">Ez a témakör leírja, hogyan ellenőrizhető a Microsoft Dynamics 365 Commerce oldaltartalmának hozzáférhetősége.</span><span class="sxs-lookup"><span data-stu-id="810d2-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="810d2-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="810d2-105">Overview</span></span>

<span data-ttu-id="810d2-106">Amikor befejezte egy oldal módosítását, győződjön meg arról, hogy a tartalom mindenki számára elérhető a weben.</span><span class="sxs-lookup"><span data-stu-id="810d2-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="810d2-107">A Commerce szerkesztőeszközök könnyen ellenőrizhető az oldal tartalmának hozzáférhetősége az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatás használatával.</span><span class="sxs-lookup"><span data-stu-id="810d2-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="810d2-108">Ez a szolgáltatás ellenőrzi az oldal tartalmát a legfrissebb [World Wide Web CONSORTIUM (W3C) akadálymentesítési](https://www.w3.org/standards/webdesign/accessibility) irányelvei alapján.</span><span class="sxs-lookup"><span data-stu-id="810d2-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="810d2-109">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integrálásának használatához be kell azt kapcsolni a bérlő vagy a webhely szintjén.</span><span class="sxs-lookup"><span data-stu-id="810d2-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="810d2-110">A Microsoft hozzáférhetőségi információk bekapcsolása a bérlő összes webhelyén</span><span class="sxs-lookup"><span data-stu-id="810d2-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="810d2-111">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a bérlő összes Commerce-webhelyén, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="810d2-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="810d2-112">A bérlői beállítások eléréséhez be kell jelentkeznie a Commerce alkalmazásba rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="810d2-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="810d2-113">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="810d2-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="810d2-114">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="810d2-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="810d2-115">A **Bérlői beállítások** részben válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="810d2-115">Under **Tenant Settings** , select **Features**.</span></span>
1. <span data-ttu-id="810d2-116">Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="810d2-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="810d2-117">A Microsoft hozzáférhetőségi információk bekapcsolása egyetlen webhelyhez</span><span class="sxs-lookup"><span data-stu-id="810d2-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="810d2-118">A [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) integráció bekapcsolásához a egyetlen Commerce-webhelyen, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="810d2-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="810d2-119">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="810d2-119">Under **Sites** , select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="810d2-120">A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="810d2-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="810d2-121">A **Webhelybeállítások** részben válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="810d2-121">Under **Site Settings** , select **Features**.</span></span>
1. <span data-ttu-id="810d2-122">Állítsa a **Hozzáférhetőség ellenőrzése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="810d2-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="810d2-123">A kezdőlapon lévő tartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="810d2-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="810d2-124">Ha az integrált [Microsoft hozzáférhetőségi információk](https://accessibilityinsights.io/) szolgáltatást szeretné használni a Commerce kezdőlapja tartalmának ellenőrzéséhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="810d2-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="810d2-125">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="810d2-125">Under **Sites** , select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="810d2-126">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="810d2-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="810d2-127">Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="810d2-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="810d2-128">Válassza a parancssáv **Hozzáférhetőség ellenőrzése** elemét.</span><span class="sxs-lookup"><span data-stu-id="810d2-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="810d2-129">Megjelenik a **Hozzáférhetőség ellenőrzése** oldal.</span><span class="sxs-lookup"><span data-stu-id="810d2-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="810d2-130">A vizsgálat befejezését követően tekintse át a jelentés tartalmát.</span><span class="sxs-lookup"><span data-stu-id="810d2-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="810d2-131">Ha valamelyik ellenőrzés sikertelen, jelölje ki az egyes sikertelen elemeket a kibontáshoz, így további részleteket is meg tud tekinteni.</span><span class="sxs-lookup"><span data-stu-id="810d2-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="810d2-132">Ha az áttekintést követően be szeretné zárni a jelentést, görgessen a **Hozzáférhetőség ellenőrzése** oldal aljára, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="810d2-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="810d2-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="810d2-133">Additional resources</span></span>

[<span data-ttu-id="810d2-134">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="810d2-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="810d2-135">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="810d2-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="810d2-136">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="810d2-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="810d2-137">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="810d2-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="810d2-138">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="810d2-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="810d2-139">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="810d2-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="810d2-140">Kategória céloldalának gazdagítása</span><span class="sxs-lookup"><span data-stu-id="810d2-140">Enrich a category landing page</span></span>](enrich-category-page.md)
