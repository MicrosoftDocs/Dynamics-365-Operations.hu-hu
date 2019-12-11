---
title: Főképmodul
description: Ez a témakör a főképmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785391"
---
# <a name="hero-module"></a><span data-ttu-id="2f43c-103">Főképmodul</span><span class="sxs-lookup"><span data-stu-id="2f43c-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2f43c-104">Ez a témakör a főképmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="2f43c-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2f43c-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="2f43c-105">Overview</span></span>

<span data-ttu-id="2f43c-106">A főképmodul a termékek és a promóciók képek és szövegek kombinálásával történő forgalmazására szolgál.</span><span class="sxs-lookup"><span data-stu-id="2f43c-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="2f43c-107">Például egy kiskereskedő felveheti a főképmodult egy e-kereskedelmi webhely kezdőlapjára egy új termék népszerűsítése céljából, és a vevők figyelmének felkeltéséhez.</span><span class="sxs-lookup"><span data-stu-id="2f43c-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="2f43c-108">A főképmodul működése a tartalomkezelő rendszer (CMS) adatain alapul.</span><span class="sxs-lookup"><span data-stu-id="2f43c-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="2f43c-109">Ez egy önálló modul, amely nem függ a lap egyéb moduljaitól.</span><span class="sxs-lookup"><span data-stu-id="2f43c-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="2f43c-110">A főképmodul a webhely bármely olyan lapján elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, akciókat vagy szolgáltatásokat).</span><span class="sxs-lookup"><span data-stu-id="2f43c-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="2f43c-111">Példák az e-Commerce főképmoduljára</span><span class="sxs-lookup"><span data-stu-id="2f43c-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="2f43c-112">A főképmodul az e-kereskedelmi webhely kezdőlapján a promóciók és az új termékek kiemelésére használható.</span><span class="sxs-lookup"><span data-stu-id="2f43c-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="2f43c-113">A termék részletes lapján a főképmodul a termék adatainak megjelenítésére használható.</span><span class="sxs-lookup"><span data-stu-id="2f43c-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="2f43c-114">Egy forgótármodulban több főképmodult lehet elhelyezni több termék vagy promóció kiemeléséhez.</span><span class="sxs-lookup"><span data-stu-id="2f43c-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="2f43c-115">Főképmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="2f43c-115">Hero module properties</span></span>

| <span data-ttu-id="2f43c-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="2f43c-116">Property name</span></span>  | <span data-ttu-id="2f43c-117">Értékek</span><span class="sxs-lookup"><span data-stu-id="2f43c-117">Values</span></span> | <span data-ttu-id="2f43c-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="2f43c-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="2f43c-119">Kép</span><span class="sxs-lookup"><span data-stu-id="2f43c-119">Image</span></span>          | <span data-ttu-id="2f43c-120">Képfájl</span><span class="sxs-lookup"><span data-stu-id="2f43c-120">Image file</span></span> | <span data-ttu-id="2f43c-121">Egy kép használható a termék vagy promóció bemutatásához.</span><span class="sxs-lookup"><span data-stu-id="2f43c-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="2f43c-122">Egy képet lehet feltölteni a képtárba, vagy egy létező kép használható.</span><span class="sxs-lookup"><span data-stu-id="2f43c-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="2f43c-123">Címsor</span><span class="sxs-lookup"><span data-stu-id="2f43c-123">Heading</span></span>        | <span data-ttu-id="2f43c-124">Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="2f43c-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="2f43c-125">Minden főképmodulhoz tartozhat fejléc.</span><span class="sxs-lookup"><span data-stu-id="2f43c-125">Every hero module can have a heading.</span></span> <span data-ttu-id="2f43c-126">Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja.</span><span class="sxs-lookup"><span data-stu-id="2f43c-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="2f43c-127">A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="2f43c-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="2f43c-128">Bekezdés</span><span class="sxs-lookup"><span data-stu-id="2f43c-128">Paragraph</span></span>      | <span data-ttu-id="2f43c-129">Bekezdés szövege</span><span class="sxs-lookup"><span data-stu-id="2f43c-129">Paragraph text</span></span> | <span data-ttu-id="2f43c-130">A főképmodulok támogatják a rich text formátumú bekezdésszövegeket.</span><span class="sxs-lookup"><span data-stu-id="2f43c-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="2f43c-131">A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások.</span><span class="sxs-lookup"><span data-stu-id="2f43c-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="2f43c-132">Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja.</span><span class="sxs-lookup"><span data-stu-id="2f43c-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="2f43c-133">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="2f43c-133">Link</span></span>           | <span data-ttu-id="2f43c-134">Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon**</span><span class="sxs-lookup"><span data-stu-id="2f43c-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="2f43c-135">A főképmodulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="2f43c-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="2f43c-136">Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges.</span><span class="sxs-lookup"><span data-stu-id="2f43c-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="2f43c-137">Az ARIA címkéknek az akadálymentességi követelmények kielégítése érdekében leírónak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2f43c-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="2f43c-138">A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva.</span><span class="sxs-lookup"><span data-stu-id="2f43c-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="2f43c-139">Szöveg elhelyezése</span><span class="sxs-lookup"><span data-stu-id="2f43c-139">Text placement</span></span> | <span data-ttu-id="2f43c-140">**Bal oldalt felül**, **Jobb oldalt felül**, **Középen fent**, **Bal oldalt alul**, **Jobb oldalt alul**, **Középen alul**, **Bal oldalt középen**, **Jobb oldalt középen** vagy **Középen középen**</span><span class="sxs-lookup"><span data-stu-id="2f43c-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="2f43c-141">Ez a tulajdonság határozza meg a kép szöveghez viszonyított pozícióját.</span><span class="sxs-lookup"><span data-stu-id="2f43c-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="2f43c-142">Ha például a **Jobbra** beállítás van kiválasztva, a kép a szövegtől jobbra jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="2f43c-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="2f43c-143">Szöveg témája</span><span class="sxs-lookup"><span data-stu-id="2f43c-143">Text theme</span></span>     | <span data-ttu-id="2f43c-144">**Világos** vagy **Sötét**</span><span class="sxs-lookup"><span data-stu-id="2f43c-144">**Light** or **Dark**</span></span> | <span data-ttu-id="2f43c-145">A szöveg számára a háttérkép alapján egy színséma adható meg.</span><span class="sxs-lookup"><span data-stu-id="2f43c-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="2f43c-146">Ha például a kép sötét háttérrel rendelkezik, akkor egy világos téma alkalmazható a szöveg láthatóbbá tételére és a színkontraszt arányára vonatkozó akadálymentességi követelmények teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2f43c-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="2f43c-147">Színátmenet</span><span class="sxs-lookup"><span data-stu-id="2f43c-147">Gradient</span></span>       | <span data-ttu-id="2f43c-148">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="2f43c-148">**True** or **False**</span></span> | <span data-ttu-id="2f43c-149">A képhez színátmenetet lehet alkalmazni a színkontraszt arányának akadálymentességi célból történő javításához.</span><span class="sxs-lookup"><span data-stu-id="2f43c-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="2f43c-150">Főképmodul hozzáadása egy új oldalhoz</span><span class="sxs-lookup"><span data-stu-id="2f43c-150">Add a hero module to a new page</span></span>

<span data-ttu-id="2f43c-151">A főképmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2f43c-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="2f43c-152">Nyissa meg a **Sablonok** lehetőséget, és hozzon létre egy **főképsablon** nevű sablont.</span><span class="sxs-lookup"><span data-stu-id="2f43c-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="2f43c-153">Az alapértelmezett lap **Fő** helyén adjon hozzá egy főképmodult.</span><span class="sxs-lookup"><span data-stu-id="2f43c-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="2f43c-154">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="2f43c-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="2f43c-155">A most létrehozott főképsablon használatával hozzon létre egy **főképlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="2f43c-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="2f43c-156">Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2f43c-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2f43c-157">A **Modul hozzáadása** párbeszédpanelen a **Modulok kiválasztása** alatt válassza ki a főképmodult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2f43c-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="2f43c-158">A bal oldali fastruktúrán válassza ki a főképmodult.</span><span class="sxs-lookup"><span data-stu-id="2f43c-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="2f43c-159">A jobb oldali tulajdonságok panelen válassza a **Kép hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f43c-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="2f43c-160">Ezt követően válasszon ki egy meglévő képet, vagy töltsön fel egy új képet.</span><span class="sxs-lookup"><span data-stu-id="2f43c-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="2f43c-161">Válassza ki a **Fejléc** elemet.</span><span class="sxs-lookup"><span data-stu-id="2f43c-161">Select **Heading**.</span></span>
1. <span data-ttu-id="2f43c-162">A **Fejléc** párbeszédpanelen adja meg a fejléc szövegét, válassza ki a címsor szintjét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2f43c-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="2f43c-163">A **Rich text** alatt írja be a szükséges szöveget.</span><span class="sxs-lookup"><span data-stu-id="2f43c-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="2f43c-164">Válassza a **Művelethivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f43c-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="2f43c-165">A **Művelethivatkozás** párbeszédpanelen adja meg a hivatkozás szövegét, a hivatkozás URL-címét és a hivatkozáshoz tartozó ARIA címkét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2f43c-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="2f43c-166">Mentse a lapot, és tekintse meg a módosítások előnézetét.</span><span class="sxs-lookup"><span data-stu-id="2f43c-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="2f43c-167">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="2f43c-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f43c-168">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2f43c-168">Additional resources</span></span>

[<span data-ttu-id="2f43c-169">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="2f43c-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2f43c-170">Figyelmeztetési modul</span><span class="sxs-lookup"><span data-stu-id="2f43c-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="2f43c-171">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="2f43c-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="2f43c-172">Tartalomgazdag blokkmodul</span><span class="sxs-lookup"><span data-stu-id="2f43c-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="2f43c-173">Tartalomelhelyezési modul</span><span class="sxs-lookup"><span data-stu-id="2f43c-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="2f43c-174">Funkciómodul</span><span class="sxs-lookup"><span data-stu-id="2f43c-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="2f43c-175">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="2f43c-175">Video player module</span></span>](add-video-player.md)
