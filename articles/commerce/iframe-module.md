---
title: iFrame modul
description: Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 4afd8f60938c99d1981be1625ef28f91d9e4bb4c
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665396"
---
# <a name="iframe-module"></a><span data-ttu-id="b9890-103">iFrame modul</span><span class="sxs-lookup"><span data-stu-id="b9890-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b9890-104">Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b9890-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b9890-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b9890-105">Overview</span></span>

<span data-ttu-id="b9890-106">Az iFrame modul egy iFrame (szövegközi keretet), amely külső tartalmat tárol a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="b9890-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="b9890-107">Felhasználható például YouTube-videó vagy PDF-megjelenítő tárolására bármilyen webhelyen.</span><span class="sxs-lookup"><span data-stu-id="b9890-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="b9890-108">Az iFrame modulhoz cél URL-cím szükséges.</span><span class="sxs-lookup"><span data-stu-id="b9890-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="b9890-109">Ezt követően egy HTML **iFrame** elemen belül tárolja a céloldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="b9890-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="b9890-110">A külső URL-címeknek a webhely tartalmi biztonsági házirendjével (CSP) kapcsolatos határozatok engedélyezett elemek listáján kell szerepelniük.</span><span class="sxs-lookup"><span data-stu-id="b9890-110">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="b9890-111">Az iFrame-tartalom esetében az URL-címeket a **keret -elődelem** utasítással kell engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="b9890-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="b9890-112">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="b9890-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b9890-113">Az iFrame modul a Dynamics 365 Commerce 10.0.13-as verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="b9890-113">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="b9890-114">A következő kép példákat mutat be azokról az iFrame modulokról, amelyek külső videókat mutatnak be meg a webhely oldalain.</span><span class="sxs-lookup"><span data-stu-id="b9890-114">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Példa a külső videókat bemutató iFrame modulokról](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="b9890-116">iFrame modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b9890-116">Iframe module properties</span></span>

| <span data-ttu-id="b9890-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="b9890-117">Property name</span></span>             | <span data-ttu-id="b9890-118">Érték</span><span class="sxs-lookup"><span data-stu-id="b9890-118">Value</span></span>                 | <span data-ttu-id="b9890-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="b9890-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b9890-120">Címsor</span><span class="sxs-lookup"><span data-stu-id="b9890-120">Heading</span></span> | <span data-ttu-id="b9890-121">Szöveg</span><span class="sxs-lookup"><span data-stu-id="b9890-121">Text</span></span> | <span data-ttu-id="b9890-122">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="b9890-122">The heading for the module.</span></span> |
| <span data-ttu-id="b9890-123">Célként megadott URL-cím</span><span class="sxs-lookup"><span data-stu-id="b9890-123">Target URL</span></span> | <span data-ttu-id="b9890-124">URL-cím</span><span class="sxs-lookup"><span data-stu-id="b9890-124">URL</span></span> | <span data-ttu-id="b9890-125">A modulban tárolt URL-cím.</span><span class="sxs-lookup"><span data-stu-id="b9890-125">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="b9890-126">Magasság</span><span class="sxs-lookup"><span data-stu-id="b9890-126">Height</span></span> | <span data-ttu-id="b9890-127">Szám vagy százalék</span><span class="sxs-lookup"><span data-stu-id="b9890-127">Number or percentage</span></span> | <span data-ttu-id="b9890-128">A modul magassága képpontban vagy százalékban kifejezve.</span><span class="sxs-lookup"><span data-stu-id="b9890-128">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="b9890-129">Például a **100** értéket a program képpontértékként kezeli, és a **100%** értéket százalékként.</span><span class="sxs-lookup"><span data-stu-id="b9890-129">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="b9890-130">Akadálymentességi címke</span><span class="sxs-lookup"><span data-stu-id="b9890-130">Aria label</span></span> | <span data-ttu-id="b9890-131">Szöveg</span><span class="sxs-lookup"><span data-stu-id="b9890-131">Text</span></span> | <span data-ttu-id="b9890-132">Az Akadálymentes dinamikus webes alkalmazások (ARIA) címkét meg lehet határozni hozzáférhetőségi célokra.</span><span class="sxs-lookup"><span data-stu-id="b9890-132">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="b9890-133">iFrame modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="b9890-133">Add an iframe module to a page</span></span>

<span data-ttu-id="b9890-134">Ha fel szeretne venni egy iFrame modult egy oldalra egy külső videó bemutatásához, akkor kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b9890-134">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="b9890-135">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9890-135">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b9890-136">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Marketingsablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="b9890-136">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b9890-137">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b9890-137">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b9890-138">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b9890-138">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="b9890-139">A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Marketingsablon** sablonját.</span><span class="sxs-lookup"><span data-stu-id="b9890-139">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="b9890-140">Az **Oldal neve** alatta adja meg a **Marketing oldalt**, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b9890-140">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="b9890-141">Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9890-141">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b9890-142">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b9890-142">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b9890-143">A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9890-143">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="b9890-144">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9890-144">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b9890-145">A **Modul hozzáadása** párbeszédpanelen válassza ki az **iFrame** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b9890-145">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b9890-146">A modul tulajdonságai ablakban állítsa be a **Cél URL-cím** értékét egy külső URL-címre a videóhoz.</span><span class="sxs-lookup"><span data-stu-id="b9890-146">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="b9890-147">Szükség szerint egyéb tulajdonságokat is megadhat, például **Fejlécet** és **Magasságot**.</span><span class="sxs-lookup"><span data-stu-id="b9890-147">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="b9890-148">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b9890-148">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b9890-149">Menjen a webhely marketing oldalára.</span><span class="sxs-lookup"><span data-stu-id="b9890-149">Go to the marketing page on your site.</span></span> <span data-ttu-id="b9890-150">Látnia kell, hogy a videó át lett renderelve az iFrame modulba.</span><span class="sxs-lookup"><span data-stu-id="b9890-150">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="b9890-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b9890-151">Additional resources</span></span>

[<span data-ttu-id="b9890-152">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="b9890-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b9890-153">Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése</span><span class="sxs-lookup"><span data-stu-id="b9890-153">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
