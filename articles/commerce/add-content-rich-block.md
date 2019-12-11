---
title: Tartalomgazdag blokkmodul
description: Ez a témakör a tartalomgazdag blokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785421"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="b63d0-103">Tartalomgazdag blokkmodul</span><span class="sxs-lookup"><span data-stu-id="b63d0-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b63d0-104">Ez a témakör a tartalomgazdag blokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b63d0-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b63d0-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b63d0-105">Overview</span></span>

<span data-ttu-id="b63d0-106">A tartalomgazdag blokkmodul egy speciális tároló, amelyben egy vagy több tartalomgazdag blokkelem helyezhető el.</span><span class="sxs-lookup"><span data-stu-id="b63d0-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="b63d0-107">A tartalomgazdag blokkmodulokat a lap szöveges tartalmaként lehet használni.</span><span class="sxs-lookup"><span data-stu-id="b63d0-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="b63d0-108">Ez a tartalom lehet tájékoztató vagy promóciós.</span><span class="sxs-lookup"><span data-stu-id="b63d0-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="b63d0-109">A tartalomgazdag blokkmoduljait a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="b63d0-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="b63d0-110">Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.</span><span class="sxs-lookup"><span data-stu-id="b63d0-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="b63d0-111">Példák az e-Commerce tartalomgazdag blokkmoduljaira</span><span class="sxs-lookup"><span data-stu-id="b63d0-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="b63d0-112">A tartalomgazdag blokkmodulokat a következő módokon lehet használni:</span><span class="sxs-lookup"><span data-stu-id="b63d0-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="b63d0-113">A termék részletes lapján a termék funkcióinak bemutatására.</span><span class="sxs-lookup"><span data-stu-id="b63d0-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="b63d0-114">Tájékoztatás céljából bármilyen oldalon.</span><span class="sxs-lookup"><span data-stu-id="b63d0-114">For informational purposes on any page.</span></span> <span data-ttu-id="b63d0-115">Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="b63d0-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="b63d0-116">Egyéni üzeneteket vehet fel a termék részletes lapjára.</span><span class="sxs-lookup"><span data-stu-id="b63d0-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="b63d0-117">(Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).</span><span class="sxs-lookup"><span data-stu-id="b63d0-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="b63d0-118">Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).</span><span class="sxs-lookup"><span data-stu-id="b63d0-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="b63d0-119">Tartalomgazdag blokkmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b63d0-119">Content rich block module properties</span></span>

| <span data-ttu-id="b63d0-120">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="b63d0-120">Property name</span></span>     | <span data-ttu-id="b63d0-121">Érték</span><span class="sxs-lookup"><span data-stu-id="b63d0-121">Value</span></span>                                 | <span data-ttu-id="b63d0-122">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="b63d0-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="b63d0-123">Oszlopok száma</span><span class="sxs-lookup"><span data-stu-id="b63d0-123">Number of columns</span></span> | <span data-ttu-id="b63d0-124">**1** és **4** közötti szám</span><span class="sxs-lookup"><span data-stu-id="b63d0-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="b63d0-125">A tartalomgazdag tömb oszlopainak száma.</span><span class="sxs-lookup"><span data-stu-id="b63d0-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="b63d0-126">Legfeljebb négy oszlop lehet.</span><span class="sxs-lookup"><span data-stu-id="b63d0-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="b63d0-127">Szélesség</span><span class="sxs-lookup"><span data-stu-id="b63d0-127">Width</span></span>             | <span data-ttu-id="b63d0-128">**Tároló kitöltése** vagy **Képernyő kitöltése**</span><span class="sxs-lookup"><span data-stu-id="b63d0-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="b63d0-129">Ha az érték **Tároló kitöltése**, akkor a tárolóban lévő elemek a tároló szélességére korlátozódnak.</span><span class="sxs-lookup"><span data-stu-id="b63d0-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="b63d0-130">Ha **Képernyő kitöltése** értékre van beállítva, akkor az elemek mérete nem korlátozódik a tároló szélességére, hanem teljes képernyős üzemmódban jelenhetnek meg.</span><span class="sxs-lookup"><span data-stu-id="b63d0-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="b63d0-131">A kívánt elrendezés elérése érdekében módosíthatja az értéket.</span><span class="sxs-lookup"><span data-stu-id="b63d0-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="b63d0-132">Tartalomgazdag blokkelem-modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b63d0-132">Content rich block item module properties</span></span>

| <span data-ttu-id="b63d0-133">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="b63d0-133">Property name</span></span> | <span data-ttu-id="b63d0-134">Érték</span><span class="sxs-lookup"><span data-stu-id="b63d0-134">Value</span></span>          | <span data-ttu-id="b63d0-135">Leírás</span><span class="sxs-lookup"><span data-stu-id="b63d0-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="b63d0-136">Bekezdés</span><span class="sxs-lookup"><span data-stu-id="b63d0-136">Paragraph</span></span>     | <span data-ttu-id="b63d0-137">Bekezdés szövege</span><span class="sxs-lookup"><span data-stu-id="b63d0-137">Paragraph text</span></span> | <span data-ttu-id="b63d0-138">Az a szöveg, amely az egyes tartalomgazdag blokkelemeket kíséri.</span><span class="sxs-lookup"><span data-stu-id="b63d0-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="b63d0-139">A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg.</span><span class="sxs-lookup"><span data-stu-id="b63d0-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="b63d0-140">Tartalomgazdag blokkmodul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="b63d0-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="b63d0-141">A tartalomgazdag blokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b63d0-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b63d0-142">Hozzon létre egy **Tartalomsablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="b63d0-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="b63d0-143">Az alapértelmezett lap **Fő** helyén adjon hozzá egy tartalomgazdag blokkmodult.</span><span class="sxs-lookup"><span data-stu-id="b63d0-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="b63d0-144">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="b63d0-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="b63d0-145">A most létrehozott tartalomsablon használatával hozzon létre egy **Tartalomlap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="b63d0-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="b63d0-146">Az új lap **Fő** helyén adjon hozzá egy tartalomgazdag blokkmodult.</span><span class="sxs-lookup"><span data-stu-id="b63d0-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="b63d0-147">A tartalomgazdag blokkmodul tulajdonságai között adja meg az oszlopok számának a **2** értéket.</span><span class="sxs-lookup"><span data-stu-id="b63d0-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="b63d0-148">A tartalomgazdag blokkmodulban válassza ki a **Modul hozzáadása** elemet, majd adjon hozzá egy tartalomgazdag blokkelemet (például **elem1**).</span><span class="sxs-lookup"><span data-stu-id="b63d0-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="b63d0-149">Adjon hozzá bekezdésszöveget az új tartalomgazdag blokkelemhez.</span><span class="sxs-lookup"><span data-stu-id="b63d0-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="b63d0-150">A tartalomgazdag blokkmodulban válassza ki a **Modul hozzáadása** elemet, majd adjon hozzá egy tartalomgazdag blokkelemet (például **elem2**).</span><span class="sxs-lookup"><span data-stu-id="b63d0-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="b63d0-151">Adjon hozzá bekezdésszöveget az új tartalomgazdag blokkelemhez.</span><span class="sxs-lookup"><span data-stu-id="b63d0-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="b63d0-152">Mentse a lapot, és tekintse meg a módosítások előnézetét.</span><span class="sxs-lookup"><span data-stu-id="b63d0-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="b63d0-153">Két rich text blokkot kell látnia kétoszlopos nézetben.</span><span class="sxs-lookup"><span data-stu-id="b63d0-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="b63d0-154">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="b63d0-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="b63d0-155">Ha hozzáad egy harmadik tartalomgazdag blokkelemet, akkor ez a korábban hozzáadott két elem alá lesz elhelyezve.</span><span class="sxs-lookup"><span data-stu-id="b63d0-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="b63d0-156">A tárolóban lévő oszlopok és cikkek számának megváltoztatásával különböző elrendezéseket érhet el a szöveges tartalomhoz.</span><span class="sxs-lookup"><span data-stu-id="b63d0-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b63d0-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b63d0-157">Additional resources</span></span>

[<span data-ttu-id="b63d0-158">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="b63d0-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b63d0-159">Figyelmeztetési modul</span><span class="sxs-lookup"><span data-stu-id="b63d0-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="b63d0-160">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="b63d0-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="b63d0-161">Tartalomelhelyezési modul</span><span class="sxs-lookup"><span data-stu-id="b63d0-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="b63d0-162">Funkciómodul</span><span class="sxs-lookup"><span data-stu-id="b63d0-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="b63d0-163">Főképmodul</span><span class="sxs-lookup"><span data-stu-id="b63d0-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="b63d0-164">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="b63d0-164">Video player module</span></span>](add-video-player.md)

