---
title: Forgótármodul
description: Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 0b4ce8fdb7b598e55db59ddf5a99a0ba46eb6f91
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986004"
---
# <a name="carousel-module"></a><span data-ttu-id="c0104-103">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="c0104-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c0104-104">Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c0104-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c0104-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c0104-105">Overview</span></span>

<span data-ttu-id="c0104-106">A forgótármodul több, a felhasználók által böngészhető promóciós elem (például multimédiás képek) forgótár-szalagcímben való elhelyezésére használható.</span><span class="sxs-lookup"><span data-stu-id="c0104-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="c0104-107">Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.</span><span class="sxs-lookup"><span data-stu-id="c0104-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="c0104-108">A forgótármodulon belül tartalomblokk-modulokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="c0104-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="c0104-109">A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.</span><span class="sxs-lookup"><span data-stu-id="c0104-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="c0104-110">Példák az e-Commerce forgótármoduljaira</span><span class="sxs-lookup"><span data-stu-id="c0104-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="c0104-111">A több promóciós modult tartalmazó forgótár használható a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="c0104-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="c0104-112">A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.</span><span class="sxs-lookup"><span data-stu-id="c0104-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="c0104-113">A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.</span><span class="sxs-lookup"><span data-stu-id="c0104-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="c0104-114">A következő kép egy kezdőoldalon használt forgótár modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c0104-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="c0104-115">Ez a forgótár modul több tartalomblokk elemet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c0104-115">This carousel module contains multiple content block items.</span></span>

![Példa egy forgótármodulra](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="c0104-117">Forgótármodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="c0104-117">Carousel module properties</span></span>

| <span data-ttu-id="c0104-118">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="c0104-118">Property name</span></span>             | <span data-ttu-id="c0104-119">Érték</span><span class="sxs-lookup"><span data-stu-id="c0104-119">Value</span></span>                 | <span data-ttu-id="c0104-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="c0104-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="c0104-121">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="c0104-121">Autoplay</span></span>                  | <span data-ttu-id="c0104-122">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="c0104-122">**True** or **False**</span></span> | <span data-ttu-id="c0104-123">Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus.</span><span class="sxs-lookup"><span data-stu-id="c0104-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="c0104-124">Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált.</span><span class="sxs-lookup"><span data-stu-id="c0104-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="c0104-125">Áttűnési időköz</span><span class="sxs-lookup"><span data-stu-id="c0104-125">Slide transition interval</span></span> | <span data-ttu-id="c0104-126">Egy érték másodpercben</span><span class="sxs-lookup"><span data-stu-id="c0104-126">A value in seconds</span></span>    | <span data-ttu-id="c0104-127">Az elemek közötti váltások intervalluma.</span><span class="sxs-lookup"><span data-stu-id="c0104-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="c0104-128">Áttűnés típusa</span><span class="sxs-lookup"><span data-stu-id="c0104-128">Transition type</span></span>           | <span data-ttu-id="c0104-129">**Csúszás** vagy **Elhalványulás**</span><span class="sxs-lookup"><span data-stu-id="c0104-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="c0104-130">A cikkek közötti áttűnési effektus.</span><span class="sxs-lookup"><span data-stu-id="c0104-130">The transition effect between items.</span></span> |
| <span data-ttu-id="c0104-131">Forgótárlapozó elrejtése</span><span class="sxs-lookup"><span data-stu-id="c0104-131">Hide carousel flipper</span></span>     | <span data-ttu-id="c0104-132">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="c0104-132">**True** or **False**</span></span> | <span data-ttu-id="c0104-133">Ha az érték beállítása **Igaz**, a forgótár-kapcsoló és a sorozatjelző el van rejtve.</span><span class="sxs-lookup"><span data-stu-id="c0104-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="c0104-134">Forgótár-elutasítás engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c0104-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="c0104-135">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="c0104-135">**True** or **False**</span></span> | <span data-ttu-id="c0104-136">Ha az érték **Igaz**, akkor a felhasználó elvetheti a forgótárat.</span><span class="sxs-lookup"><span data-stu-id="c0104-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="c0104-137">Forgótármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="c0104-137">Add a carousel module to a page</span></span>

<span data-ttu-id="c0104-138">A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c0104-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c0104-139">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0104-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c0104-140">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Forgótársablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="c0104-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="c0104-141">Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.</span><span class="sxs-lookup"><span data-stu-id="c0104-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="c0104-142">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="c0104-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="c0104-143">A most létrehozott forgótársablon használatával hozzon létre egy **Forgótárlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="c0104-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="c0104-144">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="c0104-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="c0104-145">A jobb oldali ablaktáblában adja meg a **Kitöltési képernyő** **Szélesség** értékét.</span><span class="sxs-lookup"><span data-stu-id="c0104-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="c0104-146">A **Lap körvonala** területen vegyen fel egy forgótár modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="c0104-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="c0104-147">Vegyen fel egy tartalomblokkmodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="c0104-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="c0104-148">Állítsa be a tartalomblokkmodul tulajdonságait a **Címsor**, a **Hivatkozás**, az **Elrendezés** és más tulajdonságok megadásával.</span><span class="sxs-lookup"><span data-stu-id="c0104-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="c0104-149">Adjon hozzá és konfiguráljon egy másik tartalomblokkmodult.</span><span class="sxs-lookup"><span data-stu-id="c0104-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="c0104-150">Szükség szerint beállíthat további tulajdonságokat a forgótármodulhoz.</span><span class="sxs-lookup"><span data-stu-id="c0104-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="c0104-151">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="c0104-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="c0104-152">A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul).</span><span class="sxs-lookup"><span data-stu-id="c0104-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="c0104-153">A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="c0104-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="c0104-154">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="c0104-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0104-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c0104-155">Additional resources</span></span>

[<span data-ttu-id="c0104-156">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="c0104-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c0104-157">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="c0104-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="c0104-158">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="c0104-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="c0104-159">Tartalomblokk-modul</span><span class="sxs-lookup"><span data-stu-id="c0104-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="c0104-160">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="c0104-160">Video player module</span></span>](add-video-player.md)
