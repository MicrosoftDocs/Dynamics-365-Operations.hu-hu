---
title: Előre beállított elrendezések használata
description: Ez a témakör az előre beállított elrendezésekkel végzett munkát mutatja be a Microsoft Dynamics 365 Commerce alkalmazásban.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f31dfa1fdbb3732610748abe4a9de851033f2b89
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269889"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="0c20a-103">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="0c20a-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0c20a-104">Ez a témakör az előre beállított elrendezésekkel végzett munkát mutatja be a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="0c20a-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0c20a-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0c20a-105">Overview</span></span>

<span data-ttu-id="0c20a-106">Az ebben a témakörben leírt eljárások elvégzése előtt feltétlenül olvassa az [Előre beállított és egyéni elrendezések](templates-layouts-overview.md#preset-and-custom-layouts) című részt.</span><span class="sxs-lookup"><span data-stu-id="0c20a-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="0c20a-107">Általános áttekintés: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c20a-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="0c20a-108">Új előre beállított elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="0c20a-108">Create a new preset layout</span></span>

<span data-ttu-id="0c20a-109">Kétféleképpen hozható létre kegyéni elrendezés.</span><span class="sxs-lookup"><span data-stu-id="0c20a-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="0c20a-110">Egy meglévő egyéni elrendezést új előre beállított elrendezésként menthet, vagy létrehozhat egy előre beállított elrendezést a nulláról is.</span><span class="sxs-lookup"><span data-stu-id="0c20a-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="0c20a-111">Előre beállított elrendezés létrehozása meglévő egyéni elrendezésből</span><span class="sxs-lookup"><span data-stu-id="0c20a-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="0c20a-112">Egy előre beállított elrendezés létrehozása meglévő egyéni elrendezésből kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c20a-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="0c20a-113">Nyisson meg egy olyan meglévő lapot, amely jelenleg nem használ előre beállított elrendezést, és rendelkezik egy modulstruktúrával, amelyet újra fel szeretne használni a webhely egyéb oldalain.</span><span class="sxs-lookup"><span data-stu-id="0c20a-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="0c20a-114">A lap kivételéhez válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c20a-114">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="0c20a-115">Válassza a **Mentés új elrendezésként** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c20a-115">Select **Save as new layout**.</span></span> <span data-ttu-id="0c20a-116">Megjelenik a **Mentés új elrendezésként** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="0c20a-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="0c20a-117">Írja be az előre beállított elrendezés nevét és a leírását.</span><span class="sxs-lookup"><span data-stu-id="0c20a-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="0c20a-118">A megadott értékek más szerkesztőknek is megjelennek meg, amikor új lapokat hoznak létre az elrendezéséből, vagy átváltanak arra.</span><span class="sxs-lookup"><span data-stu-id="0c20a-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="0c20a-119">Ennek megfelelően a szerzők számára hasznos értékeket adjon meg.</span><span class="sxs-lookup"><span data-stu-id="0c20a-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="0c20a-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-120">Select **OK**.</span></span>

<span data-ttu-id="0c20a-121">Az előre beállított elrendezés immár elérhető lesz, amikor új lapokat hoz létre, vagy más elrendezést választ ki egy laphoz ugyanazon sablonhierarchiában.</span><span class="sxs-lookup"><span data-stu-id="0c20a-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="0c20a-122">Annak gyors megtekintéséhez, hogy egy adott lap egy előre beállított elrendezéshez van-e kapcsolva, jelölje ki a lapot a lapok listájának nézetében, és tekintse meg az elrendezés metaadatait a jobb oldali tulajdonságok ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="0c20a-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="0c20a-123">Új előre beállított elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="0c20a-123">Create a new preset layout</span></span>

<span data-ttu-id="0c20a-124">Egy előre beállított elrendezés létrehozásához a nulláról kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c20a-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="0c20a-125">A bal oldali navigációs ablakban válassza ki az **Elrendezések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="0c20a-126">Válassza az **Új elrendezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-126">Select **New Layout**.</span></span> <span data-ttu-id="0c20a-127">Megjelenik a **Új elrendezés** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="0c20a-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="0c20a-128">Válassza ki az előre beállított elrendezéséhez használni kívánt sablont.</span><span class="sxs-lookup"><span data-stu-id="0c20a-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="0c20a-129">Írja be az előre beállított elrendezés nevét és a leírását.</span><span class="sxs-lookup"><span data-stu-id="0c20a-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="0c20a-130">A megadott értékek más szerkesztőknek is megjelennek meg, amikor új lapokat hoznak létre az elrendezéséből, vagy átváltanak arra.</span><span class="sxs-lookup"><span data-stu-id="0c20a-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="0c20a-131">Ennek megfelelően a szerzők számára hasznos értékeket adjon meg.</span><span class="sxs-lookup"><span data-stu-id="0c20a-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="0c20a-132">Kattintson az **OK** gombra az új előre beállított elrendezés létrehozásához és az elrendezésszerkesztő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0c20a-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="0c20a-133">Az elrendezésszerkesztőben a bal oldali fastruktúrában, és a jobb oldali tulajdonságok ablaktáblában adhatja meg és konfigurálhatja a modulokat.</span><span class="sxs-lookup"><span data-stu-id="0c20a-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="0c20a-134">(A folyamat hasonlít a modulok sablonokhoz történő hozzáadásának és konfigurálásának folyamatára a sablonszerkesztőben.) A modulok elrendezése és az összes zárolt alapértelmezett beállítás egy központi modulkonfigurációvá válik az összes laphoz, amely ezt az előre beállított elrendezést használja.</span><span class="sxs-lookup"><span data-stu-id="0c20a-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="0c20a-135">Előre beállított elrendezés módosítása</span><span class="sxs-lookup"><span data-stu-id="0c20a-135">Modify a preset layout</span></span>

<span data-ttu-id="0c20a-136">Egy előre beállított elrendezés módosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c20a-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="0c20a-137">A bal oldali navigációs ablakban válassza ki az **Elrendezések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="0c20a-138">Válassza ki a módosítani kívánt modult az elrendezésszerkesztő bal oldali fastruktúrájában.</span><span class="sxs-lookup"><span data-stu-id="0c20a-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="0c20a-139">Majd tegye a következők valamelyikét:</span><span class="sxs-lookup"><span data-stu-id="0c20a-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="0c20a-140">Ha a modult a szülőn belül fel-le szeretne mozgatni, akkor válassza ki a három pont gombot (**...**) a modulhoz, majd válassza a **Felfelé** vagy a **Lefelé** billentyűt.</span><span class="sxs-lookup"><span data-stu-id="0c20a-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="0c20a-141">A modul alapértelmezett beállításainak módosításához használja a tulajdonság ablaktáblát az alapértelmezett értékek megadásához, és tetszés szerint zárolja őket az összes alárendelt oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="0c20a-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="0c20a-142">Új modulok vagy töredékek a tárolómodulokhoz történő hozzáadásához válassza a három pont gombot, majd válassza a **Modul hozzáadása** vagy a **Töredék hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="0c20a-143">Ha el szeretne távolítani egy modult az elrendezésből, válassza ki a három pont gombot, majd válassza a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c20a-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="0c20a-144">Előre beállított elrendezési téma módosítása</span><span class="sxs-lookup"><span data-stu-id="0c20a-144">Change a preset layout theme</span></span>

<span data-ttu-id="0c20a-145">Általános gyakorlat az, hogy megadnak egy alapértelmezett témát az összes olyan oldalhoz, amely ez előre beállított elrendezést használja.</span><span class="sxs-lookup"><span data-stu-id="0c20a-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="0c20a-146">Ha meg szeretné adni vagy módosítani szeretné a témát az összes olyan származtatott oldal esetében, amely az előre beállított elrendezést használja, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c20a-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="0c20a-147">Válassza ki az oldaltároló modult az elrendezésszerkesztő bal oldali fastruktúrájában.</span><span class="sxs-lookup"><span data-stu-id="0c20a-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="0c20a-148">(Ez a modul általában a második csomópont, és a neve **Alapértelmezett lap**.)</span><span class="sxs-lookup"><span data-stu-id="0c20a-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="0c20a-149">Válasszon ki egy témát a jobb oldali tulajdonságok ablaktáblán a **Téma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c20a-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="0c20a-150">Előre beállított elrendezés mentése, beadása, előnézete és közzététele</span><span class="sxs-lookup"><span data-stu-id="0c20a-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="0c20a-151">Egy előre beállított elrendezés mentéséhez és beadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c20a-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="0c20a-152">Az elrendezésszerkesztő felső részén válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c20a-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="0c20a-153">A mentett módosítások nem érintik az alsóbb szintű lapokat mindaddig, amíg nincsenek beadva.</span><span class="sxs-lookup"><span data-stu-id="0c20a-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="0c20a-154">Válassza a **Szerkesztés befejezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-154">Select **Finish editing**.</span></span> <span data-ttu-id="0c20a-155">A módosítások most már felderíthetők az alsóbb szintű munkafolyamatok számára.</span><span class="sxs-lookup"><span data-stu-id="0c20a-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="0c20a-156">A módosítások előnézetéhez nyisson meg egy az előre beállított elrendezést használó meglévő lapot, vagy hozzon létre egy új lapot az elrendezésből.</span><span class="sxs-lookup"><span data-stu-id="0c20a-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="0c20a-157">Miután megtekintette az előre beállított elrendezés módosításainak előnézetét, kövesse az alábbi lépések egyikét, és tegye közzé az elrendezést az élő webhelyen:</span><span class="sxs-lookup"><span data-stu-id="0c20a-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="0c20a-158">Nyissa meg az **Elrendezések** elemet, válasszon ki egy elrendezést, majd válassza a **Közzététel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c20a-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="0c20a-159">Az elrendezésszerkesztő megnyitásához válassza ki az elrendezés nevét, majd válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c20a-159">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="0c20a-160">Egy nem közzétett elrendezésre hivatkozó lap közzététele.</span><span class="sxs-lookup"><span data-stu-id="0c20a-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="0c20a-161">A program automatikusan közzéteszi az elrendezést.</span><span class="sxs-lookup"><span data-stu-id="0c20a-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="0c20a-162">Az előre beállított elrendezések több oldalról is hivatkozhatók.</span><span class="sxs-lookup"><span data-stu-id="0c20a-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="0c20a-163">Egy előre beállított elrendezés közzététele esetén ügyeljen arra, hogy ez több oldal elrendezését is érintheti.</span><span class="sxs-lookup"><span data-stu-id="0c20a-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c20a-164">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0c20a-164">Additional resources</span></span>

[<span data-ttu-id="0c20a-165">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="0c20a-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="0c20a-166">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="0c20a-166">Work with templates</span></span>](work-with-templates.md)
