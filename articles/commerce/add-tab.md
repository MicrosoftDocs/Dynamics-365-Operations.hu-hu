---
title: Lapmodul
description: Ez a témakör ismerteti a lapmodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c865d5e055e3fadf2dda225b49f13a163974768f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797455"
---
# <a name="tab-module"></a><span data-ttu-id="383ce-103">Lapmodul</span><span class="sxs-lookup"><span data-stu-id="383ce-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="383ce-104">Ez a témakör ismerteti a lapmodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.</span><span class="sxs-lookup"><span data-stu-id="383ce-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="383ce-105">A lapmodulok olyan tárolószerű modulok, amelyek az oldalak adatainak lapokra rendszerezésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="383ce-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="383ce-106">Ezeket bármilyen oldalon fel lehet használni, ahol az információt a lapokon kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="383ce-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="383ce-107">Minden lapmodulon belül egy vagy több lapelem-modul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="383ce-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="383ce-108">Minden lapelem-modul egyetlen lapot jelent. Minden lapelem-modulhoz vagy több modul hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="383ce-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="383ce-109">Nincsenek korlátozások a lapelem-modulhoz adható modulok típusaira vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="383ce-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="383ce-110">A következő kép egy webhelyoldalon használt lapmodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="383ce-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="383ce-111">Ebben a példában a **Szállítás** lap van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="383ce-111">In this example, the **Shipping** tab selected.</span></span>

![Példa egy lapmodulra](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="383ce-113">Lapmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="383ce-113">Tab module properties</span></span>

| <span data-ttu-id="383ce-114">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="383ce-114">Property name</span></span> | <span data-ttu-id="383ce-115">Értékek</span><span class="sxs-lookup"><span data-stu-id="383ce-115">Values</span></span> | <span data-ttu-id="383ce-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="383ce-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="383ce-117">Címsor</span><span class="sxs-lookup"><span data-stu-id="383ce-117">Heading</span></span> | <span data-ttu-id="383ce-118">Szöveg</span><span class="sxs-lookup"><span data-stu-id="383ce-118">Text</span></span> | <span data-ttu-id="383ce-119">Ez a tulajdonság a lapmodul opcionális szöveges fejlécét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="383ce-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="383ce-120">Aktív lap indexe</span><span class="sxs-lookup"><span data-stu-id="383ce-120">Active Tab Index</span></span> | <span data-ttu-id="383ce-121">Szám</span><span class="sxs-lookup"><span data-stu-id="383ce-121">Number</span></span> | <span data-ttu-id="383ce-122">Ez a tulajdonság azt a lapot határozza meg, amely az oldal betöltésekor alapértelmezés szerint aktív.</span><span class="sxs-lookup"><span data-stu-id="383ce-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="383ce-123">Ha nincs megadva érték, akkor az első lapelem lesz alapértelmezés szerint aktív.</span><span class="sxs-lookup"><span data-stu-id="383ce-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="383ce-124">Lapelem-modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="383ce-124">Tab item module properties</span></span>

| <span data-ttu-id="383ce-125">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="383ce-125">Property name</span></span> | <span data-ttu-id="383ce-126">Értékek</span><span class="sxs-lookup"><span data-stu-id="383ce-126">Values</span></span> | <span data-ttu-id="383ce-127">Leírás</span><span class="sxs-lookup"><span data-stu-id="383ce-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="383ce-128">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="383ce-128">Title</span></span> | <span data-ttu-id="383ce-129">Szöveg</span><span class="sxs-lookup"><span data-stu-id="383ce-129">Text</span></span> | <span data-ttu-id="383ce-130">Ez a tulajdonság a lapmodul címszövegét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="383ce-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="383ce-131">Lapmodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="383ce-131">Add a tab module to a page</span></span>

<span data-ttu-id="383ce-132">A lapmodul felvételéhez egy oldalra, és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="383ce-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="383ce-133">Használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzletszabályzatok lap**.</span><span class="sxs-lookup"><span data-stu-id="383ce-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="383ce-134">Az **Alapértelmezett lap** **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="383ce-135">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="383ce-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="383ce-136">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="383ce-137">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lap** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="383ce-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="383ce-138">A lapmodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="383ce-139">Adja meg a címsorszöveget (például **Irányelvek**) a **Címsor szövege** területen látható **Címsor** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="383ce-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="383ce-140">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="383ce-140">Then select **OK**.</span></span>
1. <span data-ttu-id="383ce-141">A **Lap** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="383ce-142">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lapelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="383ce-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="383ce-143">A lapelem modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Kiszállítás**).</span><span class="sxs-lookup"><span data-stu-id="383ce-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="383ce-144">A **Lapelem** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="383ce-145">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="383ce-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="383ce-146">A szövegblokkmodul tulajdonságlapján adja meg a **Rich Text** alatt a szöveg bekezdését.</span><span class="sxs-lookup"><span data-stu-id="383ce-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="383ce-147">A **Lap** helyen adjon hozzá néhány további lapot, amelyeknek vannak címei.</span><span class="sxs-lookup"><span data-stu-id="383ce-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="383ce-148">Minden egyes lapelem-modulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.</span><span class="sxs-lookup"><span data-stu-id="383ce-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="383ce-149">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="383ce-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="383ce-150">Az oldal egy lap modult jelenít meg, amelyben lapelem-modulok találhatók, amelyek tartalmazzák a hozzáadott tartalmat.</span><span class="sxs-lookup"><span data-stu-id="383ce-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="383ce-151">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="383ce-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="383ce-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="383ce-152">Additional resources</span></span>

[<span data-ttu-id="383ce-153">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="383ce-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="383ce-154">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="383ce-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="383ce-155">Harmonikamodul</span><span class="sxs-lookup"><span data-stu-id="383ce-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="383ce-156">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="383ce-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]