---
title: Forgótármodul
description: Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025781"
---
# <a name="carousel-module"></a><span data-ttu-id="0bd7a-103">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="0bd7a-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0bd7a-104">Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0bd7a-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0bd7a-105">Overview</span></span>

<span data-ttu-id="0bd7a-106">A forgótármodul több, a felhasználók által böngészhető promóciós elem (például multimédiás képek) forgótár-szalagcímben való elhelyezésére használható.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="0bd7a-107">Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="0bd7a-108">A forgótármodulon belül tartalomblokk-modulokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="0bd7a-109">A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="0bd7a-110">Példák az e-Commerce forgótármoduljaira</span><span class="sxs-lookup"><span data-stu-id="0bd7a-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="0bd7a-111">A több promóciós modult tartalmazó forgótár használható a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="0bd7a-112">A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="0bd7a-113">A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="0bd7a-114">Forgótármodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="0bd7a-114">Carousel module properties</span></span>

| <span data-ttu-id="0bd7a-115">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="0bd7a-115">Property name</span></span>             | <span data-ttu-id="0bd7a-116">Érték</span><span class="sxs-lookup"><span data-stu-id="0bd7a-116">Value</span></span>                 | <span data-ttu-id="0bd7a-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="0bd7a-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="0bd7a-118">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="0bd7a-118">Autoplay</span></span>                  | <span data-ttu-id="0bd7a-119">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="0bd7a-119">**True** or **False**</span></span> | <span data-ttu-id="0bd7a-120">Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="0bd7a-121">Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="0bd7a-122">Áttűnési időköz</span><span class="sxs-lookup"><span data-stu-id="0bd7a-122">Slide transition interval</span></span> | <span data-ttu-id="0bd7a-123">Egy érték másodpercben</span><span class="sxs-lookup"><span data-stu-id="0bd7a-123">A value in seconds</span></span>    | <span data-ttu-id="0bd7a-124">Az elemek közötti váltások intervalluma.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="0bd7a-125">Áttűnés típusa</span><span class="sxs-lookup"><span data-stu-id="0bd7a-125">Transition type</span></span>           | <span data-ttu-id="0bd7a-126">**Csúszás** vagy **Elhalványulás**</span><span class="sxs-lookup"><span data-stu-id="0bd7a-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="0bd7a-127">A cikkek közötti áttűnési effektus.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-127">The transition effect between items.</span></span> |
| <span data-ttu-id="0bd7a-128">Forgótárlapozó elrejtése</span><span class="sxs-lookup"><span data-stu-id="0bd7a-128">Hide carousel flipper</span></span>     | <span data-ttu-id="0bd7a-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="0bd7a-129">**True** or **False**</span></span> | <span data-ttu-id="0bd7a-130">Ha az érték beállítása **Igaz**, a forgótár-kapcsoló és a sorozatjelző el van rejtve.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="0bd7a-131">Forgótár-elutasítás engedélyezése</span><span class="sxs-lookup"><span data-stu-id="0bd7a-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="0bd7a-132">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="0bd7a-132">**True** or **False**</span></span> | <span data-ttu-id="0bd7a-133">Ha az érték **Igaz**, akkor a felhasználó elvetheti a forgótárat.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="0bd7a-134">Forgótármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="0bd7a-134">Add a carousel module to a page</span></span>

<span data-ttu-id="0bd7a-135">A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="0bd7a-136">Hozzon létre egy **forgótársablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="0bd7a-137">Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="0bd7a-138">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="0bd7a-139">A most létrehozott forgótársablon használatával hozzon létre egy **forgótárlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="0bd7a-140">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="0bd7a-141">A jobb oldali ablaktáblában adja meg a **Kitöltési képernyő** **Szélesség** értékét.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="0bd7a-142">A **Lap körvonala** területen vegyen fel egy forgótár modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="0bd7a-143">Vegyen fel egy tartalomblokkmodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="0bd7a-144">Állítsa be a tartalomblokkmodul tulajdonságait a **Címsor**, a **Hivatkozás**, az **Elrendezés** és más tulajdonságok megadásával.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="0bd7a-145">Adjon hozzá és konfiguráljon egy másik tartalomblokkmodult.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="0bd7a-146">Szükség szerint beállíthat további tulajdonságokat a forgótármodulhoz.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="0bd7a-147">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-147">Save and preview the page.</span></span> <span data-ttu-id="0bd7a-148">A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul).</span><span class="sxs-lookup"><span data-stu-id="0bd7a-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="0bd7a-149">A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="0bd7a-150">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="0bd7a-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bd7a-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0bd7a-151">Additional resources</span></span>

[<span data-ttu-id="0bd7a-152">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="0bd7a-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0bd7a-153">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="0bd7a-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="0bd7a-154">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="0bd7a-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="0bd7a-155">Tartalomblokk modul</span><span class="sxs-lookup"><span data-stu-id="0bd7a-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="0bd7a-156">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="0bd7a-156">Video player module</span></span>](add-video-player.md)
