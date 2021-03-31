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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a08441f5dffa9c2c65b304d0265dd107a838a685
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206607"
---
# <a name="accordion-module"></a><span data-ttu-id="3e370-103">Harmonikamodul</span><span class="sxs-lookup"><span data-stu-id="3e370-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e370-104">Ez a témakör a harmonikamodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3e370-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3e370-105">A harmonikamodulok olyan tárolószerű modulok, amelyek a lapon szereplő információk vagy modulok rendszerezésére szolgálnak egy összecsukható fiókszerű képesség biztosításával.</span><span class="sxs-lookup"><span data-stu-id="3e370-105">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="3e370-106">Egy harmonikamodul használható bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="3e370-106">An accordion module can be used on any page.</span></span>

<span data-ttu-id="3e370-107">Minden harmonikamodulon belül egy vagy több harmonika cikkmodul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="3e370-107">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="3e370-108">Minden harmonika elemmodul egy összecsukható fiókot képvisel.</span><span class="sxs-lookup"><span data-stu-id="3e370-108">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="3e370-109">Minden harmonika elemmodulon belül egy vagy több modul is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="3e370-109">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="3e370-110">Nincsenek korlátozások a harmonika modulhoz adható modulok típusaira vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="3e370-110">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="3e370-111">A következő kép egy olyan harmonika modult mutat be, amely az üzlet gyakran feltett kérdéseket tartalmazó lapja adatainak rendszerezéséhez használatos.</span><span class="sxs-lookup"><span data-stu-id="3e370-111">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Példa egy harmonikamodulra](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="3e370-113">Harmonikamodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="3e370-113">Accordion module properties</span></span>

| <span data-ttu-id="3e370-114">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="3e370-114">Property name</span></span> | <span data-ttu-id="3e370-115">Értékek</span><span class="sxs-lookup"><span data-stu-id="3e370-115">Values</span></span> | <span data-ttu-id="3e370-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="3e370-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="3e370-117">Címsor</span><span class="sxs-lookup"><span data-stu-id="3e370-117">Heading</span></span> | <span data-ttu-id="3e370-118">Szöveg</span><span class="sxs-lookup"><span data-stu-id="3e370-118">Text</span></span> | <span data-ttu-id="3e370-119">Ez a tulajdonság a harmonikamodul opcionális szöveges fejlécét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3e370-119">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="3e370-120">Az összes kibontása</span><span class="sxs-lookup"><span data-stu-id="3e370-120">Expand All</span></span> | <span data-ttu-id="3e370-121">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="3e370-121">**True** or **False**</span></span> | <span data-ttu-id="3e370-122">Ha az érték **Igaz** értékre van állítva, akkor a kibontás/összecsukás funkció be van kapcsolva, így a harmonikamodul minden eleme kibontható és összecsukható lehet.</span><span class="sxs-lookup"><span data-stu-id="3e370-122">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="3e370-123">Interakció stílusa</span><span class="sxs-lookup"><span data-stu-id="3e370-123">Interaction Style</span></span> | <span data-ttu-id="3e370-124">**Független** vagy **Csak egy elem kibontása**</span><span class="sxs-lookup"><span data-stu-id="3e370-124">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="3e370-125">Ez a tulajdonság határozza meg a harmonikaelemek interakciójának stílusát.</span><span class="sxs-lookup"><span data-stu-id="3e370-125">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="3e370-126">Ha az érték **Független**, akkor minden egyes harmonika kibontható és összecsukható egymástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="3e370-126">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="3e370-127">Ha az érték **Csak egy elem kibontása** értékre van állítva , akkor egyszerre csak egy elem bontható ki.</span><span class="sxs-lookup"><span data-stu-id="3e370-127">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="3e370-128">Az elemek kibontása esetén a program összecsukja a korábban kibontott elemeket.</span><span class="sxs-lookup"><span data-stu-id="3e370-128">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="3e370-129">Harmonikamodul elemtulajdonságai</span><span class="sxs-lookup"><span data-stu-id="3e370-129">Accordion item module properties</span></span>

| <span data-ttu-id="3e370-130">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="3e370-130">Property name</span></span> | <span data-ttu-id="3e370-131">Értékek</span><span class="sxs-lookup"><span data-stu-id="3e370-131">Values</span></span> | <span data-ttu-id="3e370-132">Leírás</span><span class="sxs-lookup"><span data-stu-id="3e370-132">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="3e370-133">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="3e370-133">Title</span></span> | <span data-ttu-id="3e370-134">Szöveg</span><span class="sxs-lookup"><span data-stu-id="3e370-134">Text</span></span> | <span data-ttu-id="3e370-135">Ez a tulajdonság a harmonikamodul címszövegét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3e370-135">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="3e370-136">A cím területének kiválasztásával a felhasználók kibonthatják vagy összecsukhatják az adott részt.</span><span class="sxs-lookup"><span data-stu-id="3e370-136">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="3e370-137">Kibontás alapértelmezetten</span><span class="sxs-lookup"><span data-stu-id="3e370-137">Expand by default</span></span> | <span data-ttu-id="3e370-138">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="3e370-138">**True** or **False**</span></span> | <span data-ttu-id="3e370-139">Ha az érték **Igaz** értékre van állítva, akkor a rendszer alapértelmezés szerint kibontja a harmonika elemet a lap betöltésekor.</span><span class="sxs-lookup"><span data-stu-id="3e370-139">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="3e370-140">Harmonikamodul felvétele egy GYIK oldalra</span><span class="sxs-lookup"><span data-stu-id="3e370-140">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="3e370-141">Harmonikamodul felvételéhez egy GYIK oldalra és a tulajdonságainak beállításához az webhelykészítőben hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3e370-141">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e370-142">Nyissa meg a **Lapok**, és használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzlet GYIK**.</span><span class="sxs-lookup"><span data-stu-id="3e370-142">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="3e370-143">Az **Alapértelmezett lap** **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-143">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e370-144">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e370-144">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e370-145">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-145">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e370-146">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Harmonika** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e370-146">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e370-147">A harmonikamodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-147">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="3e370-148">A **Címsor** párbeszédpaneleben **Címsor szöveg** alatt írja be, hogy **Gyakran ismételt kérdések**.</span><span class="sxs-lookup"><span data-stu-id="3e370-148">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="3e370-149">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e370-149">Then select **OK**.</span></span>
1. <span data-ttu-id="3e370-150">A harmonika modul tulajdonságlapján jelölje be az **Összes kibontása** jelölőnégyzetet, majd az **Interakció stílusa** mezőben válassza a **Független** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3e370-150">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="3e370-151">A **Harmonika** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-151">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e370-152">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Harmonikaelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e370-152">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e370-153">A harmonika modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Hogyan működik a visszaküldés?**).</span><span class="sxs-lookup"><span data-stu-id="3e370-153">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="3e370-154">A **Harmonikaelem** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-154">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e370-155">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3e370-155">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e370-156">A szövegblokk modul tulajdonság panelén írja be a szöveg bekezdését (például **A visszaküldéseket az ügyfélszolgálaton keresztül lehet intézni. A visszaküldéshez hívja az 1-800-FABRIKAM telefonszámot. A termékre 30 napos visszaküldési irányelv tartozik. A visszaküldést ebben az időkereten belül kell kezdeményezni.**).</span><span class="sxs-lookup"><span data-stu-id="3e370-156">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="3e370-157">A **Harmonika** bővítőhelyen adjon hozzá néhány harmonikaelem modult.</span><span class="sxs-lookup"><span data-stu-id="3e370-157">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="3e370-158">Minden egyes harmonika elemmodulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.</span><span class="sxs-lookup"><span data-stu-id="3e370-158">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="3e370-159">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="3e370-159">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="3e370-160">A lap egy harmonikamodult jelenít meg, amely a hozzáadott tartalmát tartalmazta.</span><span class="sxs-lookup"><span data-stu-id="3e370-160">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="3e370-161">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="3e370-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e370-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3e370-162">Additional resources</span></span>

[<span data-ttu-id="3e370-163">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="3e370-163">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3e370-164">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="3e370-164">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3e370-165">Lapmodul</span><span class="sxs-lookup"><span data-stu-id="3e370-165">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="3e370-166">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="3e370-166">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]