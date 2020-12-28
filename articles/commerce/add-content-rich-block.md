---
title: Szövegblokk modul
description: Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412797"
---
# <a name="text-block-module"></a><span data-ttu-id="3aaa9-103">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="3aaa9-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3aaa9-104">Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3aaa9-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="3aaa9-105">Overview</span></span>

<span data-ttu-id="3aaa9-106">A szövegblokkmodul egy olyan modul, amely szöveges tartalom hozzáadására használatos.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="3aaa9-107">Ez a tartalom lehet tájékoztató vagy promóciós.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="3aaa9-108">A szövegblokkmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="3aaa9-109">Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="3aaa9-110">Példák az e-Commerce szövegblokkmoduljaira</span><span class="sxs-lookup"><span data-stu-id="3aaa9-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="3aaa9-111">A szövegblokkmodulokat a következő módokon lehet használni:</span><span class="sxs-lookup"><span data-stu-id="3aaa9-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="3aaa9-112">A termék részletes lapján a termék funkcióinak bemutatására.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="3aaa9-113">Tájékoztatás céljából bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-113">For informational purposes on any page.</span></span> <span data-ttu-id="3aaa9-114">Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="3aaa9-115">Egyéni üzeneteket vehet fel a termék részletes lapjára.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="3aaa9-116">(Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).</span><span class="sxs-lookup"><span data-stu-id="3aaa9-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="3aaa9-117">Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).</span><span class="sxs-lookup"><span data-stu-id="3aaa9-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="3aaa9-118">A következő kép egy kezdőoldalon használt szövegblokk modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-118">The following image shows an example of a text block module that is used on a home page.</span></span>

![Példa egy szövegblokk modulra](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="3aaa9-120">Szövegblokk modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="3aaa9-120">Text block module properties</span></span>

| <span data-ttu-id="3aaa9-121">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="3aaa9-121">Property name</span></span>     | <span data-ttu-id="3aaa9-122">Érték</span><span class="sxs-lookup"><span data-stu-id="3aaa9-122">Value</span></span>                                            | <span data-ttu-id="3aaa9-123">Leírás</span><span class="sxs-lookup"><span data-stu-id="3aaa9-123">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="3aaa9-124">Rich Text</span><span class="sxs-lookup"><span data-stu-id="3aaa9-124">Rich text</span></span>         | <span data-ttu-id="3aaa9-125">Rich Text</span><span class="sxs-lookup"><span data-stu-id="3aaa9-125">Rich text</span></span>                                        | <span data-ttu-id="3aaa9-126">Bekezdés szövege.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-126">Paragraph text.</span></span> <span data-ttu-id="3aaa9-127">A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-127">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="3aaa9-128">Egyéni osztály neve</span><span class="sxs-lookup"><span data-stu-id="3aaa9-128">Custom class name</span></span> | <span data-ttu-id="3aaa9-129">Az egymásra épülő stílusalapok (CSS)-osztály neve</span><span class="sxs-lookup"><span data-stu-id="3aaa9-129">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="3aaa9-130">Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-130">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="3aaa9-131">Az osztálynevet a témacsomagban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-131">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="3aaa9-132">Betűméret</span><span class="sxs-lookup"><span data-stu-id="3aaa9-132">Font size</span></span>         | <span data-ttu-id="3aaa9-133">**Kis**, **közepes**, **Nagy** vagy **Nagyon nagy**</span><span class="sxs-lookup"><span data-stu-id="3aaa9-133">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="3aaa9-134">A tartalom betűmérete.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-134">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="3aaa9-135">A szövegblokkmodul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="3aaa9-135">Add a text block module to a page</span></span>

<span data-ttu-id="3aaa9-136">A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-136">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3aaa9-137">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-137">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3aaa9-138">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Tartalomsablon** értéket.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-138">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="3aaa9-139">A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-139">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3aaa9-140">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-140">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3aaa9-141">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-141">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3aaa9-142">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-142">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="3aaa9-143">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Tartalomsablon** sablonját.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-143">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="3aaa9-144">Az **Oldal neve** alatta adja meg a **Tartalom oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-144">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="3aaa9-145">Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-145">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3aaa9-146">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-146">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3aaa9-147">A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-147">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="3aaa9-148">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-148">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3aaa9-149">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-149">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="3aaa9-150">A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-150">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="3aaa9-151">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-151">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="3aaa9-152">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="3aaa9-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3aaa9-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3aaa9-153">Additional resources</span></span>

[<span data-ttu-id="3aaa9-154">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="3aaa9-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3aaa9-155">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="3aaa9-155">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="3aaa9-156">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="3aaa9-156">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="3aaa9-157">Tartalomblokk-modul</span><span class="sxs-lookup"><span data-stu-id="3aaa9-157">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="3aaa9-158">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="3aaa9-158">Video player module</span></span>](add-video-player.md)

