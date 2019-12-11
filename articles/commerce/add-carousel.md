---
title: Forgótármodul
description: Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785237"
---
# <a name="carousel-module"></a><span data-ttu-id="64bed-103">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="64bed-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="64bed-104">Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="64bed-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="64bed-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="64bed-105">Overview</span></span>

<span data-ttu-id="64bed-106">A forgótármodul több, a felhasználók által böngészhető promóciós elem forgótárban való elhelyezésére használható.</span><span class="sxs-lookup"><span data-stu-id="64bed-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="64bed-107">Ez egy speciális tárolómodul, amely a többi modult tárolja.</span><span class="sxs-lookup"><span data-stu-id="64bed-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="64bed-108">Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.</span><span class="sxs-lookup"><span data-stu-id="64bed-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="64bed-109">A forgótármodulon belül főkép- és funkciómodulokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="64bed-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="64bed-110">A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.</span><span class="sxs-lookup"><span data-stu-id="64bed-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="64bed-111">Példák az e-Commerce forgótármoduljaira</span><span class="sxs-lookup"><span data-stu-id="64bed-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="64bed-112">A több promóciós modult tartalmazó forgótár használható a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="64bed-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="64bed-113">A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.</span><span class="sxs-lookup"><span data-stu-id="64bed-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="64bed-114">A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.</span><span class="sxs-lookup"><span data-stu-id="64bed-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="64bed-115">Forgótármodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="64bed-115">Carousel module properties</span></span>

| <span data-ttu-id="64bed-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="64bed-116">Property name</span></span>             | <span data-ttu-id="64bed-117">Érték</span><span class="sxs-lookup"><span data-stu-id="64bed-117">Value</span></span>                                | <span data-ttu-id="64bed-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="64bed-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="64bed-119">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="64bed-119">Autoplay</span></span>                  | <span data-ttu-id="64bed-120">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="64bed-120">**True** or **False**</span></span>                | <span data-ttu-id="64bed-121">Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus.</span><span class="sxs-lookup"><span data-stu-id="64bed-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="64bed-122">Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált.</span><span class="sxs-lookup"><span data-stu-id="64bed-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="64bed-123">Áttűnési időköz</span><span class="sxs-lookup"><span data-stu-id="64bed-123">Slide transition interval</span></span> | <span data-ttu-id="64bed-124">Egy érték másodpercben</span><span class="sxs-lookup"><span data-stu-id="64bed-124">A value in seconds</span></span>                   | <span data-ttu-id="64bed-125">Az elemek közötti váltások intervalluma.</span><span class="sxs-lookup"><span data-stu-id="64bed-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="64bed-126">Áttűnési animáció</span><span class="sxs-lookup"><span data-stu-id="64bed-126">Transition animation</span></span>      | <span data-ttu-id="64bed-127">**Csúszás** vagy **Elhalványulás**</span><span class="sxs-lookup"><span data-stu-id="64bed-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="64bed-128">Az áttűnési effektus.</span><span class="sxs-lookup"><span data-stu-id="64bed-128">The transition effect.</span></span> |
| <span data-ttu-id="64bed-129">Szélesség</span><span class="sxs-lookup"><span data-stu-id="64bed-129">Width</span></span>                     | <span data-ttu-id="64bed-130">**Tárolóhoz igazított** vagy **Képernyő kitöltése**</span><span class="sxs-lookup"><span data-stu-id="64bed-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="64bed-131">Ha az érték **Tárolóhoz igazított**, akkor a forgótárban lévő elemek a forgótár szélességére korlátozódnak.</span><span class="sxs-lookup"><span data-stu-id="64bed-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="64bed-132">Ha **Képernyő kitöltése** értékre van beállítva, akkor az elemek mérete nem korlátozódik a forgótár szélességére, hanem teljes képernyős üzemmódban jelenhetnek meg.</span><span class="sxs-lookup"><span data-stu-id="64bed-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="64bed-133">A kívánt elrendezés elérése érdekében módosíthatja az értéket.</span><span class="sxs-lookup"><span data-stu-id="64bed-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="64bed-134">Forgótármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="64bed-134">Add a carousel module to a page</span></span>

<span data-ttu-id="64bed-135">A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="64bed-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="64bed-136">Hozzon létre egy **forgótársablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="64bed-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="64bed-137">Az alapértelmezett lap **Fő** helyén adjon hozzá egy forgótármodult.</span><span class="sxs-lookup"><span data-stu-id="64bed-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="64bed-138">Vegyen fel egy főképmodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="64bed-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="64bed-139">Vegyen fel egy funkciómodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="64bed-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="64bed-140">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="64bed-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="64bed-141">A most létrehozott forgótársablon használatával hozzon létre egy **forgótárlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="64bed-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="64bed-142">Az új lap **Fő** helyén adjon hozzá egy forgótármodult.</span><span class="sxs-lookup"><span data-stu-id="64bed-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="64bed-143">Állítsa be a forgótármodul **Szélesség** tulajdonságát **Képernyő kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="64bed-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="64bed-144">Állítsa be az **Áttűnési animáció** tulajdonságot **Csúszás** értékre.</span><span class="sxs-lookup"><span data-stu-id="64bed-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="64bed-145">Vegyen fel egy főképmodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="64bed-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="64bed-146">A főképmodulban adjon hozzá egy képet és egy címsort, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="64bed-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="64bed-147">Vegyen fel egy funkciómodult a forgótármodulba.</span><span class="sxs-lookup"><span data-stu-id="64bed-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="64bed-148">A funkciómodulban adjon hozzá egy képet, egy címsort és egy szövegbekezdést.</span><span class="sxs-lookup"><span data-stu-id="64bed-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="64bed-149">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="64bed-149">Save and preview the page.</span></span> <span data-ttu-id="64bed-150">A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul).</span><span class="sxs-lookup"><span data-stu-id="64bed-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="64bed-151">A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="64bed-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="64bed-152">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="64bed-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64bed-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="64bed-153">Additional resources</span></span>

[<span data-ttu-id="64bed-154">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="64bed-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="64bed-155">Figyelmeztetési modul</span><span class="sxs-lookup"><span data-stu-id="64bed-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="64bed-156">Tartalomgazdag blokkmodul</span><span class="sxs-lookup"><span data-stu-id="64bed-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="64bed-157">Tartalomelhelyezési modul</span><span class="sxs-lookup"><span data-stu-id="64bed-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="64bed-158">Funkciómodul</span><span class="sxs-lookup"><span data-stu-id="64bed-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="64bed-159">Főképmodul</span><span class="sxs-lookup"><span data-stu-id="64bed-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="64bed-160">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="64bed-160">Video player module</span></span>](add-video-player.md)
