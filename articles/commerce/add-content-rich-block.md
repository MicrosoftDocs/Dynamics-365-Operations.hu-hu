---
title: Szövegblokk modul
description: Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7dbeb8785641960cc2680335436aea10775759d3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797767"
---
# <a name="text-block-module"></a><span data-ttu-id="930c0-103">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="930c0-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="930c0-104">Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="930c0-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="930c0-105">A szövegblokkmodul egy olyan modul, amely szöveges tartalom hozzáadására használatos.</span><span class="sxs-lookup"><span data-stu-id="930c0-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="930c0-106">Ez a tartalom lehet tájékoztató vagy promóciós.</span><span class="sxs-lookup"><span data-stu-id="930c0-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="930c0-107">A szövegblokkmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="930c0-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="930c0-108">Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.</span><span class="sxs-lookup"><span data-stu-id="930c0-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="930c0-109">Példák az e-Commerce szövegblokkmoduljaira</span><span class="sxs-lookup"><span data-stu-id="930c0-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="930c0-110">A szövegblokkmodulokat a következő módokon lehet használni:</span><span class="sxs-lookup"><span data-stu-id="930c0-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="930c0-111">A termék részletes lapján a termék funkcióinak bemutatására.</span><span class="sxs-lookup"><span data-stu-id="930c0-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="930c0-112">Tájékoztatás céljából bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="930c0-112">For informational purposes on any page.</span></span> <span data-ttu-id="930c0-113">Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="930c0-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="930c0-114">Egyéni üzeneteket vehet fel a termék részletes lapjára.</span><span class="sxs-lookup"><span data-stu-id="930c0-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="930c0-115">(Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).</span><span class="sxs-lookup"><span data-stu-id="930c0-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="930c0-116">Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).</span><span class="sxs-lookup"><span data-stu-id="930c0-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="930c0-117">A következő kép egy kezdőoldalon használt szövegblokk modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="930c0-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Példa egy szövegblokk modulra](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="930c0-119">Szövegblokk modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="930c0-119">Text block module properties</span></span>

| <span data-ttu-id="930c0-120">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="930c0-120">Property name</span></span>     | <span data-ttu-id="930c0-121">Érték</span><span class="sxs-lookup"><span data-stu-id="930c0-121">Value</span></span>                                            | <span data-ttu-id="930c0-122">Leírás</span><span class="sxs-lookup"><span data-stu-id="930c0-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="930c0-123">Rich Text</span><span class="sxs-lookup"><span data-stu-id="930c0-123">Rich text</span></span>         | <span data-ttu-id="930c0-124">Rich Text</span><span class="sxs-lookup"><span data-stu-id="930c0-124">Rich text</span></span>                                        | <span data-ttu-id="930c0-125">Bekezdés szövege.</span><span class="sxs-lookup"><span data-stu-id="930c0-125">Paragraph text.</span></span> <span data-ttu-id="930c0-126">A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg.</span><span class="sxs-lookup"><span data-stu-id="930c0-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="930c0-127">Egyéni osztály neve</span><span class="sxs-lookup"><span data-stu-id="930c0-127">Custom class name</span></span> | <span data-ttu-id="930c0-128">Az egymásra épülő stílusalapok (CSS)-osztály neve</span><span class="sxs-lookup"><span data-stu-id="930c0-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="930c0-129">Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát.</span><span class="sxs-lookup"><span data-stu-id="930c0-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="930c0-130">Az osztálynevet a témacsomagban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="930c0-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="930c0-131">Betűméret</span><span class="sxs-lookup"><span data-stu-id="930c0-131">Font size</span></span>         | <span data-ttu-id="930c0-132">**Kis**, **közepes**, **Nagy** vagy **Nagyon nagy**</span><span class="sxs-lookup"><span data-stu-id="930c0-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="930c0-133">A tartalom betűmérete.</span><span class="sxs-lookup"><span data-stu-id="930c0-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="930c0-134">A szövegblokkmodul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="930c0-134">Add a text block module to a page</span></span>

<span data-ttu-id="930c0-135">A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="930c0-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="930c0-136">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="930c0-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="930c0-137">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Tartalomsablon** értéket.</span><span class="sxs-lookup"><span data-stu-id="930c0-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="930c0-138">A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="930c0-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="930c0-139">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="930c0-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="930c0-140">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="930c0-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="930c0-141">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="930c0-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="930c0-142">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Tartalomsablon** sablonját.</span><span class="sxs-lookup"><span data-stu-id="930c0-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="930c0-143">Az **Oldal neve** alatta adja meg a **Tartalom oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="930c0-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="930c0-144">Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="930c0-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="930c0-145">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="930c0-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="930c0-146">A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="930c0-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="930c0-147">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="930c0-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="930c0-148">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="930c0-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="930c0-149">A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.</span><span class="sxs-lookup"><span data-stu-id="930c0-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="930c0-150">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="930c0-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="930c0-151">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="930c0-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="930c0-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="930c0-152">Additional resources</span></span>

[<span data-ttu-id="930c0-153">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="930c0-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="930c0-154">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="930c0-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="930c0-155">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="930c0-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="930c0-156">Tartalomblokk-modul</span><span class="sxs-lookup"><span data-stu-id="930c0-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="930c0-157">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="930c0-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]