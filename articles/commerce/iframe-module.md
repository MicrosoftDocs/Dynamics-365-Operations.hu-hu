---
title: iFrame modul
description: Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0616a772a416a7c9d9756a840c93b8601c08c3d0
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646951"
---
# <a name="iframe-module"></a><span data-ttu-id="8ad73-103">iFrame modul</span><span class="sxs-lookup"><span data-stu-id="8ad73-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8ad73-104">Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8ad73-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8ad73-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="8ad73-105">Overview</span></span>

<span data-ttu-id="8ad73-106">Az iFrame modul egy iFrame (szövegközi keretet), amely külső tartalmat tárol a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="8ad73-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="8ad73-107">Felhasználható például YouTube-videó vagy PDF-megjelenítő tárolására bármilyen webhelyen.</span><span class="sxs-lookup"><span data-stu-id="8ad73-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="8ad73-108">Az iFrame modulhoz cél URL-cím szükséges.</span><span class="sxs-lookup"><span data-stu-id="8ad73-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="8ad73-109">Ezt követően egy HTML **iFrame** elemen belül tárolja a céloldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="8ad73-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="8ad73-110">A külső URL-címeknek a webhely tartalmi biztonsági házirendjével (CSP) kapcsolatos határozatok engedélyezett elemek listáján (más néven „engedélyezési lista”) kell szerepelniük.</span><span class="sxs-lookup"><span data-stu-id="8ad73-110">External URLs must be on the allow list (also known as a "whitelist") per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="8ad73-111">Az iFrame-tartalom esetében az URL-címeket a **keret -elődelem** utasítással kell engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="8ad73-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="8ad73-112">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8ad73-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

<span data-ttu-id="8ad73-113">A következő kép példákat mutat be azokról az iFrame modulokról, amelyek külső videókat mutatnak be meg a webhely oldalain.</span><span class="sxs-lookup"><span data-stu-id="8ad73-113">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Példa a külső videókat bemutató iFrame modulokról](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="8ad73-115">iFrame modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="8ad73-115">Iframe module properties</span></span>

| <span data-ttu-id="8ad73-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="8ad73-116">Property name</span></span>             | <span data-ttu-id="8ad73-117">Érték</span><span class="sxs-lookup"><span data-stu-id="8ad73-117">Value</span></span>                 | <span data-ttu-id="8ad73-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="8ad73-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="8ad73-119">Címsor</span><span class="sxs-lookup"><span data-stu-id="8ad73-119">Heading</span></span> | <span data-ttu-id="8ad73-120">Szöveg</span><span class="sxs-lookup"><span data-stu-id="8ad73-120">Text</span></span> | <span data-ttu-id="8ad73-121">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="8ad73-121">The heading for the module.</span></span> |
| <span data-ttu-id="8ad73-122">Célként megadott URL-cím</span><span class="sxs-lookup"><span data-stu-id="8ad73-122">Target URL</span></span> | <span data-ttu-id="8ad73-123">URL-cím</span><span class="sxs-lookup"><span data-stu-id="8ad73-123">URL</span></span> | <span data-ttu-id="8ad73-124">A modulban tárolt URL-cím.</span><span class="sxs-lookup"><span data-stu-id="8ad73-124">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="8ad73-125">Magasság</span><span class="sxs-lookup"><span data-stu-id="8ad73-125">Height</span></span> | <span data-ttu-id="8ad73-126">Szám vagy százalék</span><span class="sxs-lookup"><span data-stu-id="8ad73-126">Number or percentage</span></span> | <span data-ttu-id="8ad73-127">A modul magassága képpontban vagy százalékban kifejezve.</span><span class="sxs-lookup"><span data-stu-id="8ad73-127">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="8ad73-128">Például a **100** értéket a program képpontértékként kezeli, és a **100%** értéket százalékként.</span><span class="sxs-lookup"><span data-stu-id="8ad73-128">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="8ad73-129">Akadálymentességi címke</span><span class="sxs-lookup"><span data-stu-id="8ad73-129">Aria label</span></span> | <span data-ttu-id="8ad73-130">Szöveg</span><span class="sxs-lookup"><span data-stu-id="8ad73-130">Text</span></span> | <span data-ttu-id="8ad73-131">Az Akadálymentes dinamikus webes alkalmazások (ARIA) címkét meg lehet határozni hozzáférhetőségi célokra.</span><span class="sxs-lookup"><span data-stu-id="8ad73-131">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="8ad73-132">iFrame modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="8ad73-132">Add an iframe module to a page</span></span>

<span data-ttu-id="8ad73-133">Ha fel szeretne venni egy iFrame modult egy oldalra egy külső videó bemutatásához, akkor kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8ad73-133">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="8ad73-134">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="8ad73-134">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="8ad73-135">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Marketingsablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="8ad73-135">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="8ad73-136">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="8ad73-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8ad73-137">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8ad73-137">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="8ad73-138">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Marketingsablon** sablonját.</span><span class="sxs-lookup"><span data-stu-id="8ad73-138">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="8ad73-139">Az **Oldal neve** alatta adja meg a **Marketing oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8ad73-139">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="8ad73-140">Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="8ad73-140">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8ad73-141">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8ad73-141">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8ad73-142">A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8ad73-142">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="8ad73-143">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="8ad73-143">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8ad73-144">A **Modul hozzáadása** párbeszédpanelen válassza ki az **iFrame** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8ad73-144">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8ad73-145">A modul tulajdonságai ablakban állítsa be a **Cél URL-cím** értékét egy külső URL-címre a videóhoz.</span><span class="sxs-lookup"><span data-stu-id="8ad73-145">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="8ad73-146">Szükség szerint egyéb tulajdonságokat is megadhat, például **Fejlécet** és **Magasságot**.</span><span class="sxs-lookup"><span data-stu-id="8ad73-146">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="8ad73-147">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="8ad73-147">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8ad73-148">Menjen a webhely marketing oldalára.</span><span class="sxs-lookup"><span data-stu-id="8ad73-148">Go to the marketing page on your site.</span></span> <span data-ttu-id="8ad73-149">Látnia kell, hogy a videó át lett renderelve az iFrame modulba.</span><span class="sxs-lookup"><span data-stu-id="8ad73-149">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="8ad73-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8ad73-150">Additional resources</span></span>

[<span data-ttu-id="8ad73-151">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="8ad73-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8ad73-152">Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése</span><span class="sxs-lookup"><span data-stu-id="8ad73-152">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
