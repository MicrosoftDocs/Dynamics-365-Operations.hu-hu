---
title: Meglévő webhelyoldal módosítása
description: Ez a témakör azt mutatja be, hogyan lehet módosítani egy létező webhelyoldalt a Microsoft Dynamics 365 Commerce megoldásban.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 87c90ed6ee62a094fe44f549c827cf9de2bf5b2f
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/17/2020
ms.locfileid: "3270004"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="18f44-103">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="18f44-103">Modify an existing site page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="18f44-104">Ez a témakör azt mutatja be, hogyan lehet módosítani egy létező webhelyoldalt a Microsoft Dynamics 365 Commerce megoldásban.</span><span class="sxs-lookup"><span data-stu-id="18f44-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="18f44-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="18f44-105">Overview</span></span>

<span data-ttu-id="18f44-106">Amikor módosítania kell egy lapot, az első lépés az, hogy megnyitja az oldalszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="18f44-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="18f44-107">Nyissa meg azt a webhelyet, amely az oldalt tartalmazza majd az oldalak listáján keresse meg a kívánt oldalt.</span><span class="sxs-lookup"><span data-stu-id="18f44-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="18f44-108">Ha nem találja az oldalt, akkor használhatja a szerkesztőeszköz bővített keresés funkcióját.</span><span class="sxs-lookup"><span data-stu-id="18f44-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="18f44-109">Írja be az oldal pontos nevét, vagy írja be az első néhány betűjét, majd egy csillagot (\*).</span><span class="sxs-lookup"><span data-stu-id="18f44-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="18f44-110">Megjelenik a lapok szűrt listája.</span><span class="sxs-lookup"><span data-stu-id="18f44-110">A filtered list of pages appears.</span></span> <span data-ttu-id="18f44-111">Ez a lista a kívánt lap megtalálására használhatja.</span><span class="sxs-lookup"><span data-stu-id="18f44-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="18f44-112">Miután megtalálta a megfelelő lapot, válassza ki a lap nevét, hogy megnyissa azt a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="18f44-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="18f44-113">Ha a lap látható a lapvizsgálóban akkor választhatja a **Szerkesztés** lehetőséget, és kiveheti az oldalt, mielőtt megnyitná azt a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="18f44-113">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="18f44-114">Ily módon egyszerre több lapot is kivehet.</span><span class="sxs-lookup"><span data-stu-id="18f44-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="18f44-115">Miután a lap a szerkesztőben meg van nyitva, győződjön meg arról, hogy az ki van-e véve az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="18f44-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="18f44-116">A szerkesztési eszközben a parancssáv dinamikus, környezetfüggő és állapotérzékeny.</span><span class="sxs-lookup"><span data-stu-id="18f44-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="18f44-117">Éppen ezért csak azokat a tevékenységeket jeleníti meg, amelyeket a lapon jelenleg végrehajthat.</span><span class="sxs-lookup"><span data-stu-id="18f44-117">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="18f44-118">Ha például a lap nincs Önhöz kivéve akkor a **Mentés** és **Szerkesztés befejezése** gomb nem jelenik meg a parancssávon.</span><span class="sxs-lookup"><span data-stu-id="18f44-118">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="18f44-119">Az ablak jobb oldalán is látható a lap állapota.</span><span class="sxs-lookup"><span data-stu-id="18f44-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="18f44-120">Ha a lap még nincs kivéve akkor a parancssávon válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-120">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="18f44-121">A parancssáv a lap új állapotának megfelelően változik.</span><span class="sxs-lookup"><span data-stu-id="18f44-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="18f44-122">Egy értesítést is kap arról, hogy a lap ki lett véve az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="18f44-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="18f44-123">A következő lépés a tényleges módosítások elvégzése.</span><span class="sxs-lookup"><span data-stu-id="18f44-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="18f44-124">Gyakran a lap bal oldalon látható faszerkezetét kell használni a módosítani kívánt modul megtalálásához és kiválasztásához, majd a jobb oldali Tulajdonságok ablaktáblán végezheti el a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="18f44-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="18f44-125">Előfordulhat azonban, hogy a változás néha modellek vagy töredékek hozzáadásával vagy eltávolításával jár.</span><span class="sxs-lookup"><span data-stu-id="18f44-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="18f44-126">Egy töredék vagy egy modul hozzáadásához használja a lap faszerkezettét és keresse meg azt a bővítőhelyet, amelyhez hozzá szeretné adni a modult vagy a töredéket, majd válassza a három pont gombot (**...**) ahhoz a bővítőhelyhez.</span><span class="sxs-lookup"><span data-stu-id="18f44-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="18f44-127">Megjelenik egy menü, amely modul vagy töredék hozzáadására szolgáló parancsokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="18f44-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="18f44-128">Egy modul vagy töredék eltávolításához keresse meg és válassza ki azt a lap fastruktúrájában, válassza ki a három pont gombot, majd válassza ki a modul vagy a töredék törlésére szolgáló parancsot.</span><span class="sxs-lookup"><span data-stu-id="18f44-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="18f44-129">Azon modulok tulajdonságait is megtekintheti és szerkesztheti, amelyek láthatók a „valós megjelenésű” (WYSIWYG) előnézetben, ha közvetlenül kiválasztja.</span><span class="sxs-lookup"><span data-stu-id="18f44-129">You can also view and edit the properties for any module that is visible in the "what you see is what you get" (WYSIWYG) preview by selecting it directly.</span></span>

<span data-ttu-id="18f44-130">Miután elkészült a módosítások elvégzésével és a hatásuk előnézetének megtekintésével, akkor adja be a lapot a **Szerkesztés befejezése** elem kiválasztásával a parancssávon.</span><span class="sxs-lookup"><span data-stu-id="18f44-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="18f44-131">Ha azonnal közzé szeretné tenni a változtatásokat, válassza a **Közzététel** elemet a parancssávon.</span><span class="sxs-lookup"><span data-stu-id="18f44-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="18f44-132">A program közzéteszi a módosított lap legutóbbi bejelentkezett változatát, és az elérhetővé válik a webhelyet megtekintő külső felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="18f44-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="18f44-133">Példa: Videó módosítása a kezdőlapon</span><span class="sxs-lookup"><span data-stu-id="18f44-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="18f44-134">A következő példa bemutatja, hogyan lehet módosítani a kezdőlap videolejátszó moduljában megjelenő videót.</span><span class="sxs-lookup"><span data-stu-id="18f44-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="18f44-135">A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="18f44-136">A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="18f44-137">Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="18f44-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="18f44-138">Válassza a parancssáv **Szerkesztés** elemét.</span><span class="sxs-lookup"><span data-stu-id="18f44-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="18f44-139">Válassza ki a **Fő** bővítőhelyet a az oldalstruktúrában.</span><span class="sxs-lookup"><span data-stu-id="18f44-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="18f44-140">A **Fő** bővítőhely alatt bontsa ki az összes folyékony tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="18f44-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="18f44-141">Keresse meg és jelölje ki a videolejátszó modulját.</span><span class="sxs-lookup"><span data-stu-id="18f44-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="18f44-142">A jobb oldali tulajdonságok ablaktáblán válassza ki a **videó** tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="18f44-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="18f44-143">Megjelenik az eszközválasztó.</span><span class="sxs-lookup"><span data-stu-id="18f44-143">The asset picker appears.</span></span>
1. <span data-ttu-id="18f44-144">Az eszközválasztóban válassza ki a rendelkezésre álló videoeszközt, vagy válassza az **Új eszköz feltöltése** lehetőséget új videoeszköz feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="18f44-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="18f44-145">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-145">Select **OK**.</span></span>
1. <span data-ttu-id="18f44-146">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="18f44-146">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="18f44-147">A **Megjegyzések** mezőbe írja be a **Videó módosítva** szöveget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="18f44-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="18f44-148">A frissített oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="18f44-149">Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="18f44-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="18f44-150">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f44-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="18f44-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="18f44-151">Additional resources</span></span>

[<span data-ttu-id="18f44-152">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="18f44-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="18f44-153">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="18f44-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="18f44-154">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="18f44-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="18f44-155">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="18f44-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="18f44-156">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="18f44-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="18f44-157">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="18f44-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="18f44-158">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="18f44-158">Verify page content accessibility</span></span>](verify-accessibility.md)
