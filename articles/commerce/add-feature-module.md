---
title: Funkciómodul
description: Ez a témakör a funkciómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785284"
---
# <a name="feature-module"></a><span data-ttu-id="79ecd-103">Funkciómodul</span><span class="sxs-lookup"><span data-stu-id="79ecd-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="79ecd-104">Ez a témakör a funkciómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="79ecd-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="79ecd-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="79ecd-105">Overview</span></span>

<span data-ttu-id="79ecd-106">A funkciómodul a termékek és a promóciók képek és szövegek kombinálásával történő forgalmazására szolgál.</span><span class="sxs-lookup"><span data-stu-id="79ecd-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="79ecd-107">Például egy kiskereskedő hozzáadhat egy funkciómodult a termék részletes lapjához a termék funkcióinak kiemeléséhez.</span><span class="sxs-lookup"><span data-stu-id="79ecd-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="79ecd-108">A funkció modul működése a tartalomkezelő rendszer (CMS) adatain alapul.</span><span class="sxs-lookup"><span data-stu-id="79ecd-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="79ecd-109">Ez egy önálló modul, amely nem függ a lap egyéb moduljaitól.</span><span class="sxs-lookup"><span data-stu-id="79ecd-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="79ecd-110">A funkciómodul a webhely bármely olyan lapján elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, akciókat vagy szolgáltatásokat).</span><span class="sxs-lookup"><span data-stu-id="79ecd-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="79ecd-111">Példák az e-Commerce funkciómoduljaira</span><span class="sxs-lookup"><span data-stu-id="79ecd-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="79ecd-112">A következő lapokon használható a funkciómodul:</span><span class="sxs-lookup"><span data-stu-id="79ecd-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="79ecd-113">A termék részletes lapja a termék funkcióinak bemutatására</span><span class="sxs-lookup"><span data-stu-id="79ecd-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="79ecd-114">A termékek népszerűsítésére szolgáló kezdőlap.</span><span class="sxs-lookup"><span data-stu-id="79ecd-114">The home page, to promote products</span></span>
- <span data-ttu-id="79ecd-115">Kategória lap egy termékkategória kiemeléséhez</span><span class="sxs-lookup"><span data-stu-id="79ecd-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="79ecd-116">Funkciómodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="79ecd-116">Feature module properties</span></span>

| <span data-ttu-id="79ecd-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="79ecd-117">Property name</span></span>     | <span data-ttu-id="79ecd-118">Értékek</span><span class="sxs-lookup"><span data-stu-id="79ecd-118">Values</span></span> | <span data-ttu-id="79ecd-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="79ecd-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="79ecd-120">Kép</span><span class="sxs-lookup"><span data-stu-id="79ecd-120">Image</span></span>             | <span data-ttu-id="79ecd-121">Képfájl</span><span class="sxs-lookup"><span data-stu-id="79ecd-121">Image file</span></span> | <span data-ttu-id="79ecd-122">Egy kép használható a termék vagy promóció reklámozásához.</span><span class="sxs-lookup"><span data-stu-id="79ecd-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="79ecd-123">Egy képet lehet feltölteni a képtárba, vagy egy létező kép használható.</span><span class="sxs-lookup"><span data-stu-id="79ecd-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="79ecd-124">Címsor</span><span class="sxs-lookup"><span data-stu-id="79ecd-124">Heading</span></span>           | <span data-ttu-id="79ecd-125">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="79ecd-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="79ecd-126">Minden funkciómodulhoz tartozhat fejléc.</span><span class="sxs-lookup"><span data-stu-id="79ecd-126">Every feature module can have a heading.</span></span> <span data-ttu-id="79ecd-127">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="79ecd-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="79ecd-128">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="79ecd-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="79ecd-129">Bekezdés</span><span class="sxs-lookup"><span data-stu-id="79ecd-129">Paragraph</span></span>         | <span data-ttu-id="79ecd-130">Bekezdés szövege</span><span class="sxs-lookup"><span data-stu-id="79ecd-130">Paragraph text</span></span> | <span data-ttu-id="79ecd-131">A funkciómodulok támogatják a multimédiás szöveg formátumú bekezdésszövegeket.</span><span class="sxs-lookup"><span data-stu-id="79ecd-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="79ecd-132">A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások.</span><span class="sxs-lookup"><span data-stu-id="79ecd-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="79ecd-133">Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja.</span><span class="sxs-lookup"><span data-stu-id="79ecd-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="79ecd-134">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="79ecd-134">Link</span></span>              | <span data-ttu-id="79ecd-135">Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon**</span><span class="sxs-lookup"><span data-stu-id="79ecd-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="79ecd-136">A funkciómodulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="79ecd-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="79ecd-137">Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges.</span><span class="sxs-lookup"><span data-stu-id="79ecd-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="79ecd-138">Az ARIA címkéknek az akadálymentességi követelmények kielégítése érdekében leírónak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="79ecd-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="79ecd-139">A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva.</span><span class="sxs-lookup"><span data-stu-id="79ecd-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="79ecd-140">Kép elhelyezése</span><span class="sxs-lookup"><span data-stu-id="79ecd-140">Image placement</span></span>   | <span data-ttu-id="79ecd-141">**Jobbra**, **Balra**, **Felül** vagy **Alul**</span><span class="sxs-lookup"><span data-stu-id="79ecd-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="79ecd-142">Ez a tulajdonság határozza meg a kép szöveghez viszonyított pozícióját.</span><span class="sxs-lookup"><span data-stu-id="79ecd-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="79ecd-143">Ha például a **Jobbra** beállítás van kiválasztva, a kép a szövegtől jobbra jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="79ecd-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="79ecd-144">Képoszlop mérete</span><span class="sxs-lookup"><span data-stu-id="79ecd-144">Image column size</span></span> | <span data-ttu-id="79ecd-145">Egy **1** és **12** közötti érték</span><span class="sxs-lookup"><span data-stu-id="79ecd-145">A value from **1** through **12**</span></span> | <span data-ttu-id="79ecd-146">Ez a tulajdonság határozza meg a kép szöveghez viszonyított méretét.</span><span class="sxs-lookup"><span data-stu-id="79ecd-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="79ecd-147">A méret a lapon található oszlopok számában van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="79ecd-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="79ecd-148">A lapon 12 oszlop van.</span><span class="sxs-lookup"><span data-stu-id="79ecd-148">There are 12 columns on a page.</span></span> <span data-ttu-id="79ecd-149">Alapértelmezés szerint a kép és a szöveg mérete azonos (hat oszlop mindegyik).</span><span class="sxs-lookup"><span data-stu-id="79ecd-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="79ecd-150">A méret azonban igény szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="79ecd-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="79ecd-151">Funkciómodul felvétele egy új lapra</span><span class="sxs-lookup"><span data-stu-id="79ecd-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="79ecd-152">A funkciómodul új lapra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="79ecd-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="79ecd-153">Nyissa meg a **Sablonok** lehetőséget, és hozzon létre egy **funkciósablon** nevű sablont.</span><span class="sxs-lookup"><span data-stu-id="79ecd-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="79ecd-154">Az alapértelmezett lap **Fő** helyén adjon hozzá egy funkciómodult.</span><span class="sxs-lookup"><span data-stu-id="79ecd-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="79ecd-155">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="79ecd-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="79ecd-156">A most létrehozott funkciósablon használatával hozzon létre egy **funkciólap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="79ecd-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="79ecd-157">Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="79ecd-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="79ecd-158">A **Modul hozzáadása** párbeszédpanelen a **Modulok kiválasztása** alatt válasszon ki egy funkciómodult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="79ecd-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="79ecd-159">A bal oldali fastruktúrán válassza ki a funkciómodult.</span><span class="sxs-lookup"><span data-stu-id="79ecd-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="79ecd-160">A jobb oldali tulajdonságok panelen válassza a **Kép hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79ecd-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="79ecd-161">Ezt követően válasszon ki egy meglévő képet, vagy töltsön fel egy új képet.</span><span class="sxs-lookup"><span data-stu-id="79ecd-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="79ecd-162">Válassza ki a **Fejléc** elemet.</span><span class="sxs-lookup"><span data-stu-id="79ecd-162">Select **Heading**.</span></span>
1. <span data-ttu-id="79ecd-163">A **Fejléc** párbeszédpanelen adja meg a fejléc szövegét, válassza ki a címsor szintjét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="79ecd-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="79ecd-164">A **Rich text** alatt írja be a szükséges szöveget.</span><span class="sxs-lookup"><span data-stu-id="79ecd-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="79ecd-165">Válassza a **Művelethivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79ecd-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="79ecd-166">A **Művelethivatkozás** párbeszédpanelen adja meg a hivatkozás szövegét, a hivatkozás URL-címét és a hivatkozáshoz tartozó ARIA címkét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="79ecd-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="79ecd-167">Mentse a lapot, és tekintse meg a módosítások előnézetét.</span><span class="sxs-lookup"><span data-stu-id="79ecd-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="79ecd-168">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="79ecd-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79ecd-169">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="79ecd-169">Additional resources</span></span>

[<span data-ttu-id="79ecd-170">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="79ecd-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="79ecd-171">Figyelmeztetési modul</span><span class="sxs-lookup"><span data-stu-id="79ecd-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="79ecd-172">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="79ecd-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="79ecd-173">Tartalomgazdag blokkmodul</span><span class="sxs-lookup"><span data-stu-id="79ecd-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="79ecd-174">Tartalomelhelyezési modul</span><span class="sxs-lookup"><span data-stu-id="79ecd-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="79ecd-175">Főképmodul</span><span class="sxs-lookup"><span data-stu-id="79ecd-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="79ecd-176">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="79ecd-176">Video player module</span></span>](add-video-player.md)
