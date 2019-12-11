---
title: Oldal mentése, megtekintése és közzététele
description: Ez a témakör azt mutatja be, hogyan lehet egy lapot menteni, megtekinteni előnézetét vagy közzétenni azt a Microsoft Dynamics 365 Commerce webhelyén.
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
ms.openlocfilehash: 8c1b82b1b8423c63d442ee581ed0cc8789ee63fd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697888"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="881a4-103">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="881a4-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="881a4-104">Ez a témakör azt mutatja be, hogyan lehet egy lapot menteni, megtekinteni előnézetét vagy közzétenni azt a Microsoft Dynamics 365 Commerce webhelyén.</span><span class="sxs-lookup"><span data-stu-id="881a4-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="881a4-105">Egy lap mentése</span><span class="sxs-lookup"><span data-stu-id="881a4-105">Save a page</span></span>

<span data-ttu-id="881a4-106">Lap mentéséhez ki kell vennie azt, és meg kell nyitnia azt a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="881a4-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="881a4-107">A módosítást követően azonnal mentenie kell azt, hogy garantálni lehessen azt, hogy a módosítások tárolva legyenek.</span><span class="sxs-lookup"><span data-stu-id="881a4-107">You should save a page immediately after you modify it, to help guarantee that your changes are stored.</span></span>

<span data-ttu-id="881a4-108">A lapok mentésekor a módosítások csak az Ön számára láthatók.</span><span class="sxs-lookup"><span data-stu-id="881a4-108">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="881a4-109">A mentési művelet elsősorban a módosítások tárolására szolgál, amíg a lap még nincs készen a beadásra.</span><span class="sxs-lookup"><span data-stu-id="881a4-109">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="881a4-110">Amikor befejezte a lap módosítását, ajánlott beadni azt, hogy a módosítások mások számára is láthatóvá váljanak.</span><span class="sxs-lookup"><span data-stu-id="881a4-110">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="881a4-111">Ezen a ponton a lapot más olyan felhasználók is kivehetik, akik módosítania szeretnék azt.</span><span class="sxs-lookup"><span data-stu-id="881a4-111">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="881a4-112">Egy lap előnézetének megtekintése</span><span class="sxs-lookup"><span data-stu-id="881a4-112">Preview a page</span></span>

<span data-ttu-id="881a4-113">A szerkesztő eszköz kétféle előnézeti funkciót kínál: a „valós megjelenítésű” (WYSIWYG) előnézeti ablak a lap szerkesztőjében és egy külön előnézeti ablak.</span><span class="sxs-lookup"><span data-stu-id="881a4-113">The authoring tool offers two kinds of preview features: a "what you see is what you get" (WYSIWYG) preview pane in the page editor and a separate preview window.</span></span>

<span data-ttu-id="881a4-114">A lapszerkesztő használata közben a központ ablaktáblájában megjelenik a „valós megejelenítésű” (WYSIWYG) előnézet.</span><span class="sxs-lookup"><span data-stu-id="881a4-114">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="881a4-115">A program automatikusan frissíti ezt az előnézetet a lap mentésekor.</span><span class="sxs-lookup"><span data-stu-id="881a4-115">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="881a4-116">A parancssori **Frissítés** lehetőséget kiválaszva manuálisan is frissítheti ezt.</span><span class="sxs-lookup"><span data-stu-id="881a4-116">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="881a4-117">A WYSIWYG előnézete ugyanúgy jeleníti meg a lapot, ahogy a webhely felhasználói látni fogják, de felette láthatók a szerkesztői segédeszközök.</span><span class="sxs-lookup"><span data-stu-id="881a4-117">The WYSIWYG preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="881a4-118">Ha befejezte a lap módosítását, megtekintheti előnézetét, tehát azt, hogy a vásárlók mit fognak látni.</span><span class="sxs-lookup"><span data-stu-id="881a4-118">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="881a4-119">A lap előnézetéhez válassza a parancssáv **Előnézet** elemét.</span><span class="sxs-lookup"><span data-stu-id="881a4-119">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="881a4-120">Az előnézet egy külön böngészőablakban fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="881a4-120">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="881a4-121">Az előnézeti ablak lapja ugyanúgy jelenik meg, ahogy a webhely felhasználója látni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="881a4-121">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="881a4-122">Az ablak átméretezésével meggyőződhet arról, hogy a reszponzív modulok helyesen legyenek megjelenítve minden nézetben.</span><span class="sxs-lookup"><span data-stu-id="881a4-122">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="881a4-123">A nem közzétett tartalom előnézetéhez hitelesítés és megfelelő engedélyek szükségesek.</span><span class="sxs-lookup"><span data-stu-id="881a4-123">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="881a4-124">Ezért ha megosztja az előnézeti URL-címet valakivel, akkor az adott személynek rendelkeznie kell a tartalom eléréséhez szükséges engedélyekkel.</span><span class="sxs-lookup"><span data-stu-id="881a4-124">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="881a4-125">Oldal közzététele</span><span class="sxs-lookup"><span data-stu-id="881a4-125">Publish a page</span></span>

<span data-ttu-id="881a4-126">Amikor elkészült a lap, a következő lépés a közzététel, hogy a külső felhasználók megtekinthessék a tartalmat.</span><span class="sxs-lookup"><span data-stu-id="881a4-126">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="881a4-127">A lap közzététele előtt be kell küldenie azt.</span><span class="sxs-lookup"><span data-stu-id="881a4-127">Before you can publish a page, you must check it in.</span></span>

<span data-ttu-id="881a4-128">A lapokat akár a lapvizsgálóból és a lapszerkesztőből is közzéteheti vagy megszüntetheti a közzétételt.</span><span class="sxs-lookup"><span data-stu-id="881a4-128">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="881a4-129">A lapvizsgáló megjeleníti a lapok listáját, és kötegelt művelteket is lehetővé tesz.</span><span class="sxs-lookup"><span data-stu-id="881a4-129">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="881a4-130">A lapszerkesztőben csak azokat a lapokat lehet közzétenni vagy a közzétételt megszüntetni, amelyek meg vannak nyitva.</span><span class="sxs-lookup"><span data-stu-id="881a4-130">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="881a4-131">Ha egy vagy több oldalt szeretne közzétenni a lapvizsgálóból, jelölje ki a lapokat, győződjön meg arról, hogy be vannak küldve, majd válassza a **Közzététel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="881a4-131">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="881a4-132">A program közzéteszi a lapokat, és értesítést kap a műveletről a szerkesztőeszközben.</span><span class="sxs-lookup"><span data-stu-id="881a4-132">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="881a4-133">Ha egyetlen lapot szeretne közzétenni a lapszerkesztőből, akkor az eljárás hasonló.</span><span class="sxs-lookup"><span data-stu-id="881a4-133">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="881a4-134">Amíg a lap meg van nyitva a lapszerkesztőben, győződjön meg arról, hogy az be van küldve, majd válassza a **Közzététel** elemet a parancssoron.</span><span class="sxs-lookup"><span data-stu-id="881a4-134">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="881a4-135">A program közzéteszi a lapot, és értesítést kap a műveletről a szerkesztőeszközben.</span><span class="sxs-lookup"><span data-stu-id="881a4-135">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="881a4-136">Amikor közzétesz egy oldalt, csak az oldal tartalmát teszi közzé a program.</span><span class="sxs-lookup"><span data-stu-id="881a4-136">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="881a4-137">Ön és a többi felhasználó csak azután tekintheti meg a lapot, ha ahhoz társítottak egy URL-címet.</span><span class="sxs-lookup"><span data-stu-id="881a4-137">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="881a4-138">Az URL-címet külön kell közzé tenni.</span><span class="sxs-lookup"><span data-stu-id="881a4-138">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="881a4-139">A lap közzététele előtt minden olyan képet vagy töredéket is közzé kell tenni, amelyre a lap hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="881a4-139">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="881a4-140">Kezdőlap mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="881a4-140">Save, preview, and publish a home page</span></span>

<span data-ttu-id="881a4-141">Kezdőlap mentéséhez, előnézetéhez és közzétételéhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="881a4-141">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="881a4-142">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-142">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="881a4-143">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-143">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="881a4-144">Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="881a4-144">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="881a4-145">Válassza a **Kivétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-145">Select **Check Out**.</span></span>
1. <span data-ttu-id="881a4-146">Igény szerint módosítsa a lapot.</span><span class="sxs-lookup"><span data-stu-id="881a4-146">Modify the page as you require.</span></span>
1. <span data-ttu-id="881a4-147">Válassza a **Mentés** parancsot, majd válassza a **Beadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="881a4-147">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="881a4-148">A **Megjegyzések** mezőbe írja be a végrehajtott változtatásokkal kapcsolatos megjegyzését, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="881a4-148">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="881a4-149">A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-149">Select **Preview** to preview your page.</span></span> <span data-ttu-id="881a4-150">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="881a4-150">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="881a4-151">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-151">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="881a4-152">URL-cím közzététele</span><span class="sxs-lookup"><span data-stu-id="881a4-152">Publish a URL</span></span>

<span data-ttu-id="881a4-153">Egy URL-cím közzétételéhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="881a4-153">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="881a4-154">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-154">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="881a4-155">A bal oldali navigációs ablakban válassza ki az **URL-címek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="881a4-155">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="881a4-156">Keresse meg és válassza ki a közzétenni kívánt URL-címet.</span><span class="sxs-lookup"><span data-stu-id="881a4-156">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="881a4-157">Válassza a parancssáv **Közzététel** elemét.</span><span class="sxs-lookup"><span data-stu-id="881a4-157">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="881a4-158">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="881a4-158">Additional resources</span></span>

[<span data-ttu-id="881a4-159">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="881a4-159">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="881a4-160">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="881a4-160">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="881a4-161">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="881a4-161">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="881a4-162">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="881a4-162">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="881a4-163">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="881a4-163">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="881a4-164">Kategória céloldalának gazdagítása</span><span class="sxs-lookup"><span data-stu-id="881a4-164">Enrich a category landing page</span></span>](enrich-category-page.md)

