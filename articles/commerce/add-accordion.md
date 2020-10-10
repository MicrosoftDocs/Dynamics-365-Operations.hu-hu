---
title: Harmonikamodul
description: Ez a témakör a harmonikamodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 2bb18539f610e5af05f8d9a20a0ba9f34db5c94f
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817134"
---
# <a name="accordion-module"></a><span data-ttu-id="5ff08-103">Harmonikamodul</span><span class="sxs-lookup"><span data-stu-id="5ff08-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5ff08-104">Ez a témakör a harmonikamodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5ff08-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5ff08-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5ff08-105">Overview</span></span>

<span data-ttu-id="5ff08-106">A harmonikamodulok olyan tárolószerű modulok, amelyek a lapon szereplő információk vagy modulok rendszerezésére szolgálnak egy összecsukható fiókszerű képesség biztosításával.</span><span class="sxs-lookup"><span data-stu-id="5ff08-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="5ff08-107">Egy harmonikamodul használható bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="5ff08-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="5ff08-108">Minden harmonikamodulon belül egy vagy több harmonika cikkmodul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="5ff08-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="5ff08-109">Minden harmonika elemmodul egy összecsukható fiókot képvisel.</span><span class="sxs-lookup"><span data-stu-id="5ff08-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="5ff08-110">Minden harmonika elemmodulon belül egy vagy több modul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="5ff08-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="5ff08-111">Nincsenek korlátozások a harmonika modulhoz adható modulok típusaira vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="5ff08-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="5ff08-112">A következő kép egy olyan harmonika modult mutat be, amely az üzlet gyakran feltett kérdéseket tartalmazó lapja adatainak rendszerezéséhez használatos.</span><span class="sxs-lookup"><span data-stu-id="5ff08-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Példa egy harmonikamodulra](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="5ff08-114">Harmonikamodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="5ff08-114">Accordion module properties</span></span>

| <span data-ttu-id="5ff08-115">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="5ff08-115">Property name</span></span> | <span data-ttu-id="5ff08-116">Értékek</span><span class="sxs-lookup"><span data-stu-id="5ff08-116">Values</span></span> | <span data-ttu-id="5ff08-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="5ff08-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="5ff08-118">Címsor</span><span class="sxs-lookup"><span data-stu-id="5ff08-118">Heading</span></span> | <span data-ttu-id="5ff08-119">Szöveg</span><span class="sxs-lookup"><span data-stu-id="5ff08-119">Text</span></span> | <span data-ttu-id="5ff08-120">Ez a tulajdonság a harmonikamodul opcionális szöveges fejlécét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="5ff08-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="5ff08-121">Az összes kibontása</span><span class="sxs-lookup"><span data-stu-id="5ff08-121">Expand All</span></span> | <span data-ttu-id="5ff08-122">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="5ff08-122">**True** or **False**</span></span> | <span data-ttu-id="5ff08-123">Ha az érték **Igaz** értékre van állítva, akkor a kibontás/összecsukás funkció be van kapcsolva, így a harmonikamodul minden eleme kibontható és összecsukható lehet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="5ff08-124">Interakció stílusa</span><span class="sxs-lookup"><span data-stu-id="5ff08-124">Interaction Style</span></span> | <span data-ttu-id="5ff08-125">**Független** vagy **Csak egy elem kibontása**</span><span class="sxs-lookup"><span data-stu-id="5ff08-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="5ff08-126">Ez a tulajdonság határozza meg a harmonikaelemek interakciójának stílusát.</span><span class="sxs-lookup"><span data-stu-id="5ff08-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="5ff08-127">Ha az érték **Független**, akkor minden egyes harmonika kibontható és összecsukható egymástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="5ff08-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="5ff08-128">Ha az érték **Csak egy elem kibontása** értékre van állítva , akkor egyszerre csak egy elem bontható ki.</span><span class="sxs-lookup"><span data-stu-id="5ff08-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="5ff08-129">Az elemek kibontása esetén a program összecsukja a korábban kibontott elemeket.</span><span class="sxs-lookup"><span data-stu-id="5ff08-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="5ff08-130">Harmonikamodul elemtulajdonságai</span><span class="sxs-lookup"><span data-stu-id="5ff08-130">Accordion item module properties</span></span>

| <span data-ttu-id="5ff08-131">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="5ff08-131">Property name</span></span> | <span data-ttu-id="5ff08-132">Értékek</span><span class="sxs-lookup"><span data-stu-id="5ff08-132">Values</span></span> | <span data-ttu-id="5ff08-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="5ff08-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="5ff08-134">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="5ff08-134">Title</span></span> | <span data-ttu-id="5ff08-135">Szöveg</span><span class="sxs-lookup"><span data-stu-id="5ff08-135">Text</span></span> | <span data-ttu-id="5ff08-136">Ez a tulajdonság a harmonikamodul címszövegét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="5ff08-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="5ff08-137">A cím területének kiválasztásával a felhasználók kibonthatják vagy összecsukhatják az adott részt.</span><span class="sxs-lookup"><span data-stu-id="5ff08-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="5ff08-138">Kibontás alapértelmezetten</span><span class="sxs-lookup"><span data-stu-id="5ff08-138">Expand by default</span></span> | <span data-ttu-id="5ff08-139">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="5ff08-139">**True** or **False**</span></span> | <span data-ttu-id="5ff08-140">Ha az érték **Igaz** értékre van állítva, akkor a rendszer alapértelmezés szerint kibontja a harmonika elemet a lap betöltésekor.</span><span class="sxs-lookup"><span data-stu-id="5ff08-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="5ff08-141">Harmonikamodul felvétele egy GYIK oldalra</span><span class="sxs-lookup"><span data-stu-id="5ff08-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="5ff08-142">Harmonikamodul felvételéhez egy GYIK oldalra és a tulajdonságainak beállításához az webhelykészítőben hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5ff08-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="5ff08-143">Nyissa meg a **Lapok**, és használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzlet GYIK**.</span><span class="sxs-lookup"><span data-stu-id="5ff08-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="5ff08-144">Az **Alapértelmezett lap** **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5ff08-145">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5ff08-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5ff08-146">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5ff08-147">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Harmonika** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5ff08-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5ff08-148">A harmonikamodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="5ff08-149">A **Címsor** párbeszédpaneleben **Címsor szöveg** alatt írja be, hogy **Gyakran ismételt kérdések**.</span><span class="sxs-lookup"><span data-stu-id="5ff08-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="5ff08-150">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ff08-150">Then select **OK**.</span></span>
1. <span data-ttu-id="5ff08-151">A harmonika modul tulajdonságlapján jelölje be az **Összes kibontása** jelölőnégyzetet, majd az **Interakció stílusa** mezőben válassza a **Független** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5ff08-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="5ff08-152">A **Harmonika** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5ff08-153">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Harmonikaelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5ff08-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5ff08-154">A harmonika modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Hogyan működik a visszaküldés?**).</span><span class="sxs-lookup"><span data-stu-id="5ff08-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="5ff08-155">A **Harmonikaelem** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5ff08-156">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5ff08-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5ff08-157">A szövegblokk modul tulajdonság panelén írja be a szöveg bekezdését (például **A visszaküldéseket az ügyfélszolgálaton keresztül lehet intézni. A visszaküldéshez hívja az 1-800-FABRIKAM telefonszámot. A termékre 30 napos visszaküldési irányelv tartozik. A visszaküldést ebben az időkereten belül kell kezdeményezni.**).</span><span class="sxs-lookup"><span data-stu-id="5ff08-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="5ff08-158">A **Harmonika** bővítőhelyen adjon hozzá néhány harmonikaelem modult.</span><span class="sxs-lookup"><span data-stu-id="5ff08-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="5ff08-159">Minden egyes harmonika elemmodulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.</span><span class="sxs-lookup"><span data-stu-id="5ff08-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="5ff08-160">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="5ff08-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="5ff08-161">A lap egy harmonikamodult jelenít meg, amely a hozzáadott tartalmát tartalmazta.</span><span class="sxs-lookup"><span data-stu-id="5ff08-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="5ff08-162">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="5ff08-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ff08-163">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5ff08-163">Additional resources</span></span>

[<span data-ttu-id="5ff08-164">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="5ff08-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5ff08-165">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="5ff08-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="5ff08-166">Lapmodul</span><span class="sxs-lookup"><span data-stu-id="5ff08-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="5ff08-167">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="5ff08-167">Text block module</span></span>](add-content-rich-block.md)
