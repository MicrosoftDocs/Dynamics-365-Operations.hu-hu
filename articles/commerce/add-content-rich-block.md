---
title: Szövegblokk modul
description: Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025597"
---
# <a name="text-block-module"></a><span data-ttu-id="ba3a6-103">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="ba3a6-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ba3a6-104">Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ba3a6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ba3a6-105">Overview</span></span>

<span data-ttu-id="ba3a6-106">A szövegblokkmodul egy olyan modul, amely szöveges tartalom hozzáadására használatos.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="ba3a6-107">Ez a tartalom lehet tájékoztató vagy promóciós.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="ba3a6-108">A szövegblokkmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="ba3a6-109">Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="ba3a6-110">Példák az e-Commerce szövegblokkmoduljaira</span><span class="sxs-lookup"><span data-stu-id="ba3a6-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="ba3a6-111">A szövegblokkmodulokat a következő módokon lehet használni:</span><span class="sxs-lookup"><span data-stu-id="ba3a6-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="ba3a6-112">A termék részletes lapján a termék funkcióinak bemutatására.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="ba3a6-113">Tájékoztatás céljából bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-113">For informational purposes on any page.</span></span> <span data-ttu-id="ba3a6-114">Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="ba3a6-115">Egyéni üzeneteket vehet fel a termék részletes lapjára.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="ba3a6-116">(Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).</span><span class="sxs-lookup"><span data-stu-id="ba3a6-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="ba3a6-117">Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).</span><span class="sxs-lookup"><span data-stu-id="ba3a6-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="ba3a6-118">Szövegblokk modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="ba3a6-118">Text block module properties</span></span>

| <span data-ttu-id="ba3a6-119">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="ba3a6-119">Property name</span></span>     | <span data-ttu-id="ba3a6-120">Value</span><span class="sxs-lookup"><span data-stu-id="ba3a6-120">Value</span></span>                                            | <span data-ttu-id="ba3a6-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="ba3a6-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="ba3a6-122">Rich Text</span><span class="sxs-lookup"><span data-stu-id="ba3a6-122">Rich text</span></span>         | <span data-ttu-id="ba3a6-123">Rich Text</span><span class="sxs-lookup"><span data-stu-id="ba3a6-123">Rich text</span></span>                                        | <span data-ttu-id="ba3a6-124">Bekezdés szövege.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-124">Paragraph text.</span></span> <span data-ttu-id="ba3a6-125">A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="ba3a6-126">Egyéni osztály neve</span><span class="sxs-lookup"><span data-stu-id="ba3a6-126">Custom class name</span></span> | <span data-ttu-id="ba3a6-127">Az egymásra épülő stílusalapok (CSS)-osztály neve</span><span class="sxs-lookup"><span data-stu-id="ba3a6-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="ba3a6-128">Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="ba3a6-129">Az osztálynevet a témacsomagban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="ba3a6-130">Betűméret</span><span class="sxs-lookup"><span data-stu-id="ba3a6-130">Font size</span></span>         | <span data-ttu-id="ba3a6-131">**Kis**, **közepes**, **Nagy**vagy **Nagyon nagy**</span><span class="sxs-lookup"><span data-stu-id="ba3a6-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="ba3a6-132">A tartalom betűmérete.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="ba3a6-133">A szövegblokkmodul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="ba3a6-133">Add a text block module to a page</span></span>

<span data-ttu-id="ba3a6-134">A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ba3a6-135">Hozzon létre egy **Tartalomsablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="ba3a6-136">Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="ba3a6-137">Fejezze be a sablon szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="ba3a6-138">A most létrehozott tartalomsablon használatával hozzon létre egy **Tartalomlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="ba3a6-139">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="ba3a6-140">A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="ba3a6-141">Vegyen fel egy szövegblokkmodult a tárolómodulba.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="ba3a6-142">A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="ba3a6-143">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba3a6-144">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ba3a6-144">Additional resources</span></span>

[<span data-ttu-id="ba3a6-145">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="ba3a6-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ba3a6-146">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="ba3a6-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="ba3a6-147">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="ba3a6-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="ba3a6-148">Tartalomblokk modul</span><span class="sxs-lookup"><span data-stu-id="ba3a6-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="ba3a6-149">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="ba3a6-149">Video player module</span></span>](add-video-player.md)

