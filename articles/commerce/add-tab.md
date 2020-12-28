---
title: Lapmodul
description: Ez a témakör a lapmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c9d897113442f14b95539efb9fec9482be96447a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412806"
---
# <a name="tab-module"></a><span data-ttu-id="718ce-103">Lapmodul</span><span class="sxs-lookup"><span data-stu-id="718ce-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="718ce-104">Ez a témakör a lapmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="718ce-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="718ce-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="718ce-105">Overview</span></span>

<span data-ttu-id="718ce-106">A lapmodulok olyan tárolószerű modulok, amelyek az oldalak adatainak lapokra rendszerezésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="718ce-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="718ce-107">Ezeket bármilyen oldalon fel lehet használni, ahol az információt a lapokon kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="718ce-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="718ce-108">Minden lapmodulon belül egy vagy több lapelem-modul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="718ce-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="718ce-109">Minden lapelem-modul egyetlen lapot jelent. Minden lapelem-modulhoz vagy több modul hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="718ce-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="718ce-110">Nincsenek korlátozások a lapelem-modulhoz adható modulok típusaira vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="718ce-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="718ce-111">A következő kép egy webhelyoldalon használt lapmodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="718ce-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="718ce-112">Ebben a példában a **Szállítás** lap van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="718ce-112">In this example, the **Shipping** tab selected.</span></span>

![Példa egy lapmodulra](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="718ce-114">Lapmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="718ce-114">Tab module properties</span></span>

| <span data-ttu-id="718ce-115">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="718ce-115">Property name</span></span> | <span data-ttu-id="718ce-116">Értékek</span><span class="sxs-lookup"><span data-stu-id="718ce-116">Values</span></span> | <span data-ttu-id="718ce-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="718ce-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="718ce-118">Címsor</span><span class="sxs-lookup"><span data-stu-id="718ce-118">Heading</span></span> | <span data-ttu-id="718ce-119">Szöveg</span><span class="sxs-lookup"><span data-stu-id="718ce-119">Text</span></span> | <span data-ttu-id="718ce-120">Ez a tulajdonság a lapmodul opcionális szöveges fejlécét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="718ce-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="718ce-121">Aktív lap indexe</span><span class="sxs-lookup"><span data-stu-id="718ce-121">Active Tab Index</span></span> | <span data-ttu-id="718ce-122">Szám</span><span class="sxs-lookup"><span data-stu-id="718ce-122">Number</span></span> | <span data-ttu-id="718ce-123">Ez a tulajdonság azt a lapot határozza meg, amely az oldal betöltésekor alapértelmezés szerint aktív.</span><span class="sxs-lookup"><span data-stu-id="718ce-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="718ce-124">Ha nincs megadva érték, akkor az első lapelem lesz alapértelmezés szerint aktív.</span><span class="sxs-lookup"><span data-stu-id="718ce-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="718ce-125">Lapelem-modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="718ce-125">Tab item module properties</span></span>

| <span data-ttu-id="718ce-126">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="718ce-126">Property name</span></span> | <span data-ttu-id="718ce-127">Értékek</span><span class="sxs-lookup"><span data-stu-id="718ce-127">Values</span></span> | <span data-ttu-id="718ce-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="718ce-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="718ce-129">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="718ce-129">Title</span></span> | <span data-ttu-id="718ce-130">Szöveg</span><span class="sxs-lookup"><span data-stu-id="718ce-130">Text</span></span> | <span data-ttu-id="718ce-131">Ez a tulajdonság a lapmodul címszövegét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="718ce-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="718ce-132">Lapmodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="718ce-132">Add a tab module to a page</span></span>

<span data-ttu-id="718ce-133">A lapmodul felvételéhez egy oldalra, és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="718ce-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="718ce-134">Használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzletszabályzatok lap**.</span><span class="sxs-lookup"><span data-stu-id="718ce-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="718ce-135">Az **Alapértelmezett lap** **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="718ce-136">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="718ce-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="718ce-137">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="718ce-138">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lap** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="718ce-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="718ce-139">A lapmodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="718ce-140">Adja meg a címsorszöveget (például **Irányelvek**) a **Címsor szövege** területen látható **Címsor** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="718ce-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="718ce-141">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="718ce-141">Then select **OK**.</span></span>
1. <span data-ttu-id="718ce-142">A **Lap** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="718ce-143">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lapelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="718ce-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="718ce-144">A lapelem modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Kiszállítás**).</span><span class="sxs-lookup"><span data-stu-id="718ce-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="718ce-145">A **Lapelem** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="718ce-146">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="718ce-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="718ce-147">A szövegblokkmodul tulajdonságlapján adja meg a **Rich Text** alatt a szöveg bekezdését.</span><span class="sxs-lookup"><span data-stu-id="718ce-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="718ce-148">A **Lap** helyen adjon hozzá néhány további lapot, amelyeknek vannak címei.</span><span class="sxs-lookup"><span data-stu-id="718ce-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="718ce-149">Minden egyes lapelem-modulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.</span><span class="sxs-lookup"><span data-stu-id="718ce-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="718ce-150">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="718ce-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="718ce-151">Az oldal egy lap modult jelenít meg, amelyben lapelem-modulok találhatók, amelyek tartalmazzák a hozzáadott tartalmat.</span><span class="sxs-lookup"><span data-stu-id="718ce-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="718ce-152">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="718ce-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="718ce-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="718ce-153">Additional resources</span></span>

[<span data-ttu-id="718ce-154">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="718ce-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="718ce-155">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="718ce-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="718ce-156">Harmonikamodul</span><span class="sxs-lookup"><span data-stu-id="718ce-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="718ce-157">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="718ce-157">Text block module</span></span>](add-content-rich-block.md)
