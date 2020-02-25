---
title: Videólejátszó modul
description: Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025648"
---
# <a name="video-player-module"></a><span data-ttu-id="59b72-103">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="59b72-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="59b72-104">Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="59b72-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="59b72-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="59b72-105">Overview</span></span>

<span data-ttu-id="59b72-106">A videólejátszó modul a videólejátszás támogatására szolgál.</span><span class="sxs-lookup"><span data-stu-id="59b72-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="59b72-107">A tartalmat bármilyen oldalra felveheti, feltéve, hogy a videotartalom feltöltése a tartalomkezelő rendszerben (CMS) történik.</span><span class="sxs-lookup"><span data-stu-id="59b72-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="59b72-108">A videolejátszó modul támogatja az .mp4 média típusát.</span><span class="sxs-lookup"><span data-stu-id="59b72-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="59b72-109">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="59b72-109">Video player module</span></span>

<span data-ttu-id="59b72-110">A videólejátszó modul egy e-kereskedelmi webhelyről származó videók bemutatására használható.</span><span class="sxs-lookup"><span data-stu-id="59b72-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="59b72-111">Támogatja az összes lejátszási funkciót, például a lejátszást, szüneteltetést, teljes méretű módot, audioleírásokat és a feliratokat.</span><span class="sxs-lookup"><span data-stu-id="59b72-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="59b72-112">A videólejátszó modul a Microsoft akadálymentesítési szabványoknak való megfelelés érdekében támogatja a feliratok testreszabását is.</span><span class="sxs-lookup"><span data-stu-id="59b72-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="59b72-113">Testreszabhatja például a betűméretet és a háttérszínt.</span><span class="sxs-lookup"><span data-stu-id="59b72-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="59b72-114">A videólejátszó modul támogatja a másodlagos hangsávot is.</span><span class="sxs-lookup"><span data-stu-id="59b72-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="59b72-115">Videó CMS-be való feltöltése esetén másodlagos hangsávot is fel lehet tölteni.</span><span class="sxs-lookup"><span data-stu-id="59b72-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="59b72-116">A videólejátszó modul lejátszhatja a másodlagos hangsávot, ha a felhasználó kiválasztja azt.</span><span class="sxs-lookup"><span data-stu-id="59b72-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="59b72-117">Példák az e-kereskedelem videólejátszó moduljaira</span><span class="sxs-lookup"><span data-stu-id="59b72-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="59b72-118">Tájékoztató videók a termék részletes lapjain vagy marketinglapjain</span><span class="sxs-lookup"><span data-stu-id="59b72-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="59b72-119">Promóciós videók vagy irányelvekkel kapcsolatos videók bármelyik marketinglapon</span><span class="sxs-lookup"><span data-stu-id="59b72-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="59b72-120">A termék jellemzőit bemutató marketingvideók a termék részletes lapjain vagy marketinglapokon</span><span class="sxs-lookup"><span data-stu-id="59b72-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="59b72-121">Videólejátszó modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="59b72-121">Video player module properties</span></span>

| <span data-ttu-id="59b72-122">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="59b72-122">Property name</span></span>         | <span data-ttu-id="59b72-123">Érték</span><span class="sxs-lookup"><span data-stu-id="59b72-123">Value</span></span>                               | <span data-ttu-id="59b72-124">Leírás</span><span class="sxs-lookup"><span data-stu-id="59b72-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="59b72-125">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="59b72-125">Auto play</span></span>             | <span data-ttu-id="59b72-126">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-126">**True** or **False**</span></span>               | <span data-ttu-id="59b72-127">Ha **Igaz** értékre van beállítva, akkor a program automatikusan lejátssza a videót.</span><span class="sxs-lookup"><span data-stu-id="59b72-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="59b72-128">Elnémítás</span><span class="sxs-lookup"><span data-stu-id="59b72-128">Mute</span></span>                  | <span data-ttu-id="59b72-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-129">**True** or **False**</span></span>               | <span data-ttu-id="59b72-130">Ha **Igaz** értékre van beállítva, akkor a hang le van némítva.</span><span class="sxs-lookup"><span data-stu-id="59b72-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="59b72-131">Ennél a lejátszónál az alapértelmezett érték **Hamis**.</span><span class="sxs-lookup"><span data-stu-id="59b72-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="59b72-132">A Chrome böngészőben alapértelmezés szerint az automatikusan lejátszott videók némítva vannak, és a hang lejátszása csak akkor történik meg, ha a felhasználó manuálisan játssza le a videót.</span><span class="sxs-lookup"><span data-stu-id="59b72-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="59b72-133">Ciklus</span><span class="sxs-lookup"><span data-stu-id="59b72-133">Loop</span></span>                  | <span data-ttu-id="59b72-134">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-134">**True** or **False**</span></span>               | <span data-ttu-id="59b72-135">Ha **Igaz** értékre van beállítva, akkor a program a videót ismétlődő hurokban játssza le.</span><span class="sxs-lookup"><span data-stu-id="59b72-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="59b72-136">Média</span><span class="sxs-lookup"><span data-stu-id="59b72-136">Media</span></span>                 | <span data-ttu-id="59b72-137">Videófájl elérési útja és neve</span><span class="sxs-lookup"><span data-stu-id="59b72-137">Video file path and name</span></span> | <span data-ttu-id="59b72-138">A videólejátszó által lejátszott videófájl.</span><span class="sxs-lookup"><span data-stu-id="59b72-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="59b72-139">Teljes képernyős lejátszás</span><span class="sxs-lookup"><span data-stu-id="59b72-139">Play fullscreen</span></span>       | <span data-ttu-id="59b72-140">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-140">**True** or **False**</span></span>               | <span data-ttu-id="59b72-141">Ha **Igaz** értékre van beállítva, akkor a program a videót teljes képernyős üzemmódban játssza le.</span><span class="sxs-lookup"><span data-stu-id="59b72-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="59b72-142">Lejátszás/szüneteltetés eseményindítója</span><span class="sxs-lookup"><span data-stu-id="59b72-142">Play pause trigger</span></span>    | <span data-ttu-id="59b72-143">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-143">**True** or **False**</span></span>               | <span data-ttu-id="59b72-144">Ha **Igaz** értékre van állítva, akkor egy lejátszás/szünet gomb jelenik meg a videón.</span><span class="sxs-lookup"><span data-stu-id="59b72-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="59b72-145">Videolejátszó vezérlői</span><span class="sxs-lookup"><span data-stu-id="59b72-145">Video player controls</span></span> | <span data-ttu-id="59b72-146">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-146">**True** or **False**</span></span>               | <span data-ttu-id="59b72-147">Ha **Igaz** értékre van beállítva, akkor az összes videolejátszó-vezérlő látható.</span><span class="sxs-lookup"><span data-stu-id="59b72-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="59b72-148">Ezek közé a vezérlőelemek közé tartozik a lejátszás és szünet gomb, a folyamatjelző és a feliratbeállítások.</span><span class="sxs-lookup"><span data-stu-id="59b72-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="59b72-149">Plakátkép elrejtése</span><span class="sxs-lookup"><span data-stu-id="59b72-149">Hide poster image</span></span>     | <span data-ttu-id="59b72-150">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="59b72-150">**True** or **False**</span></span>               | <span data-ttu-id="59b72-151">A videó poszterkerettel jelenhet meg.</span><span class="sxs-lookup"><span data-stu-id="59b72-151">A video can have a poster frame.</span></span> <span data-ttu-id="59b72-152">Ha a tulajdonság értéke **Igaz**, akkor a program elrejti a poszterkeretet.</span><span class="sxs-lookup"><span data-stu-id="59b72-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="59b72-153">Maszk szintje</span><span class="sxs-lookup"><span data-stu-id="59b72-153">Mask level</span></span>            | <span data-ttu-id="59b72-154">**0** és **100** közötti szám</span><span class="sxs-lookup"><span data-stu-id="59b72-154">A number from **0** through **100**</span></span> | <span data-ttu-id="59b72-155">A stílus módosításához a videóra alkalmazott maszk.</span><span class="sxs-lookup"><span data-stu-id="59b72-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="59b72-156">Videólejátszó modul hozzáadása egy laphoz</span><span class="sxs-lookup"><span data-stu-id="59b72-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="59b72-157">A videolejátszó modul létrehozása előtt fel kell töltenie egy videót a médiatárba.</span><span class="sxs-lookup"><span data-stu-id="59b72-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="59b72-158">A videólejátszó modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="59b72-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="59b72-159">Hozzon létre egy **videólejátszó sablon** nevű lapsablont.</span><span class="sxs-lookup"><span data-stu-id="59b72-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="59b72-160">Az alapértelmezett lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="59b72-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="59b72-161">A tárolómodulban adja hozzá a videólejátszó és háttérvideó-lejátszó modulokat.</span><span class="sxs-lookup"><span data-stu-id="59b72-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="59b72-162">Fejezze be a sablon szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="59b72-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="59b72-163">A létrehozott videólejátszó sablon használatával hozzon létre egy **videólejátszó lap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="59b72-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="59b72-164">Az új lap **Fő** helyén adjon hozzá egy videólejátszó modult.</span><span class="sxs-lookup"><span data-stu-id="59b72-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="59b72-165">A videolejátszó modul tulajdonságlapján válassza a **Videó hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="59b72-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="59b72-166">A **Médiaválasztó** párbeszédablakon válasszon egy videót, majd válassza az **Új médiaelem feltöltése** elemet.</span><span class="sxs-lookup"><span data-stu-id="59b72-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="59b72-167">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="59b72-167">Save and preview the page.</span></span> <span data-ttu-id="59b72-168">A lapon a videómodulnak látszania kell.</span><span class="sxs-lookup"><span data-stu-id="59b72-168">You should see the video module on the page.</span></span> <span data-ttu-id="59b72-169">A további beállítások módosításával testreszabhatja a modul viselkedését.</span><span class="sxs-lookup"><span data-stu-id="59b72-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="59b72-170">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="59b72-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59b72-171">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="59b72-171">Additional resources</span></span>

[<span data-ttu-id="59b72-172">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="59b72-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="59b72-173">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="59b72-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="59b72-174">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="59b72-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="59b72-175">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="59b72-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="59b72-176">Tartalomblokk modul</span><span class="sxs-lookup"><span data-stu-id="59b72-176">Content block module</span></span>](add-hero-module.md)
