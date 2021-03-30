---
title: Forgótármodul
description: Ez a témakör ismerteti a forgótármodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.
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
ms.openlocfilehash: 5333ecd7a1fe4f60684fa5f5bb3ac9f98efde6d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206511"
---
# <a name="carousel-module"></a><span data-ttu-id="1633c-103">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="1633c-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1633c-104">Ez a témakör ismerteti a forgótármodulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.</span><span class="sxs-lookup"><span data-stu-id="1633c-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1633c-105">A forgótármodul több, a felhasználók által böngészhető promóciós elem (például multimédiás képek) forgótár-szalagcímben való elhelyezésére használható.</span><span class="sxs-lookup"><span data-stu-id="1633c-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="1633c-106">Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.</span><span class="sxs-lookup"><span data-stu-id="1633c-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="1633c-107">A forgótármodulon belül tartalomblokk-modulokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="1633c-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="1633c-108">A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.</span><span class="sxs-lookup"><span data-stu-id="1633c-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="1633c-109">Példák az e-Commerce forgótármoduljaira</span><span class="sxs-lookup"><span data-stu-id="1633c-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="1633c-110">A több promóciós modult tartalmazó forgótár használható a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="1633c-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="1633c-111">A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.</span><span class="sxs-lookup"><span data-stu-id="1633c-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="1633c-112">A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.</span><span class="sxs-lookup"><span data-stu-id="1633c-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="1633c-113">A következő kép egy kezdőoldalon használt forgótár modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="1633c-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="1633c-114">Ez a forgótár modul több tartalomblokk elemet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1633c-114">This carousel module contains multiple content block items.</span></span>

![Példa egy forgótármodulra](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="1633c-116">Forgótármodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="1633c-116">Carousel module properties</span></span>

| <span data-ttu-id="1633c-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="1633c-117">Property name</span></span>             | <span data-ttu-id="1633c-118">Érték</span><span class="sxs-lookup"><span data-stu-id="1633c-118">Value</span></span>                 | <span data-ttu-id="1633c-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="1633c-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="1633c-120">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="1633c-120">Autoplay</span></span>                  | <span data-ttu-id="1633c-121">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="1633c-121">**True** or **False**</span></span> | <span data-ttu-id="1633c-122">Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus.</span><span class="sxs-lookup"><span data-stu-id="1633c-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="1633c-123">Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált.</span><span class="sxs-lookup"><span data-stu-id="1633c-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="1633c-124">Áttűnési időköz</span><span class="sxs-lookup"><span data-stu-id="1633c-124">Slide transition interval</span></span> | <span data-ttu-id="1633c-125">Egy érték másodpercben</span><span class="sxs-lookup"><span data-stu-id="1633c-125">A value in seconds</span></span>    | <span data-ttu-id="1633c-126">Az elemek közötti váltások intervalluma.</span><span class="sxs-lookup"><span data-stu-id="1633c-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="1633c-127">Áttűnés típusa</span><span class="sxs-lookup"><span data-stu-id="1633c-127">Transition type</span></span>           | <span data-ttu-id="1633c-128">**Csúszás** vagy **Elhalványulás**</span><span class="sxs-lookup"><span data-stu-id="1633c-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="1633c-129">A cikkek közötti áttűnési effektus.</span><span class="sxs-lookup"><span data-stu-id="1633c-129">The transition effect between items.</span></span> |
| <span data-ttu-id="1633c-130">Forgótárlapozó elrejtése</span><span class="sxs-lookup"><span data-stu-id="1633c-130">Hide carousel flipper</span></span>     | <span data-ttu-id="1633c-131">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="1633c-131">**True** or **False**</span></span> | <span data-ttu-id="1633c-132">Ha az érték beállítása **Igaz**, a forgótár-kapcsoló és a sorozatjelző el van rejtve.</span><span class="sxs-lookup"><span data-stu-id="1633c-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="1633c-133">Forgótár-elutasítás engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1633c-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="1633c-134">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="1633c-134">**True** or **False**</span></span> | <span data-ttu-id="1633c-135">Ha az érték **Igaz**, akkor a felhasználó elvetheti a forgótárat.</span><span class="sxs-lookup"><span data-stu-id="1633c-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="1633c-136">Forgótármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="1633c-136">Add a carousel module to a page</span></span>

<span data-ttu-id="1633c-137">A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1633c-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="1633c-138">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="1633c-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="1633c-139">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Forgótársablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="1633c-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="1633c-140">Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.</span><span class="sxs-lookup"><span data-stu-id="1633c-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="1633c-141">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="1633c-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="1633c-142">A most létrehozott forgótársablon használatával hozzon létre egy **Forgótárlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="1633c-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="1633c-143">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="1633c-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="1633c-144">A jobb oldali ablaktáblában adja meg a **Kitöltési képernyő** **Szélesség** értékét.</span><span class="sxs-lookup"><span data-stu-id="1633c-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="1633c-145">A **Lap körvonala** területen vegyen fel egy forgótár modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="1633c-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="1633c-146">Vegyen fel egy tartalomblokkmodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="1633c-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="1633c-147">Állítsa be a tartalomblokkmodul tulajdonságait a **Címsor**, a **Hivatkozás**, az **Elrendezés** és más tulajdonságok megadásával.</span><span class="sxs-lookup"><span data-stu-id="1633c-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="1633c-148">Adjon hozzá és konfiguráljon egy másik tartalomblokkmodult.</span><span class="sxs-lookup"><span data-stu-id="1633c-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="1633c-149">Szükség szerint beállíthat további tulajdonságokat a forgótármodulhoz.</span><span class="sxs-lookup"><span data-stu-id="1633c-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="1633c-150">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="1633c-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="1633c-151">A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul).</span><span class="sxs-lookup"><span data-stu-id="1633c-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="1633c-152">A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="1633c-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="1633c-153">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="1633c-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1633c-154">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1633c-154">Additional resources</span></span>

[<span data-ttu-id="1633c-155">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="1633c-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1633c-156">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="1633c-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="1633c-157">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="1633c-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="1633c-158">Tartalomblokk-modul</span><span class="sxs-lookup"><span data-stu-id="1633c-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="1633c-159">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="1633c-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]