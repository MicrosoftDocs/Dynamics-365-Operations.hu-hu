---
title: Modul feltérképezése
description: Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646950"
---
# <a name="map-module"></a><span data-ttu-id="ef3b8-103">Modul feltérképezése</span><span class="sxs-lookup"><span data-stu-id="ef3b8-103">Map module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="ef3b8-104">Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ef3b8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ef3b8-105">Overview</span></span>

<span data-ttu-id="ef3b8-106">A modul feltérképezése egy interaktív térképen jeleníti meg az üzleteket, amelyeket a [8. verziós Bing Térképek webes vezérlő](https://docs.microsoft.com/bingmaps/v8-web-control/) használatával renderelnek.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="ef3b8-107">A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce központ megosztott paraméterei oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="ef3b8-108">A modul feltérképezése különböző nézeteket nyújt – például közúti, légi és utcai –, amelyekkel a felhasználók megtekinthetik a leképezési helyeket.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="ef3b8-109">Olyan interakciókat is lehetővé tesznek, mint például a nagyítás és a felhasználó helyének használata.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="ef3b8-110">A modul feltérképezése az üzletválasztó modullal együtt dolgozik a térképeken megjelenített üzletek földrajzi helyeinek meghatározásában.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="ef3b8-111">Az üzletválasztó és a modul feltérképezések akkor lépnek interakcióba, ha a felhasználó a webhely egyik moduljában kiválaszt egy üzletet.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="ef3b8-112">A modul feltérképezések az üzletválasztó modulokkal való interakción túl más forgatókönyvek esetén is kiterjeszthetőek.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="ef3b8-113">Azonban a modul testreszabása kötelező.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-113">However, module customization is required.</span></span>

<span data-ttu-id="ef3b8-114">A modul feltérképezése a Commerce 10.0.13 verziójában lett bevezetve.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="ef3b8-115">A következő kép egy üzlet oldalán használt letérképezési modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Példa egy üzletválasztó modulra](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="ef3b8-117">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="ef3b8-117">Module properties</span></span>

| <span data-ttu-id="ef3b8-118">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="ef3b8-118">Property name</span></span>             | <span data-ttu-id="ef3b8-119">Érték</span><span class="sxs-lookup"><span data-stu-id="ef3b8-119">Value</span></span>                 | <span data-ttu-id="ef3b8-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="ef3b8-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="ef3b8-121">Címsor</span><span class="sxs-lookup"><span data-stu-id="ef3b8-121">Heading</span></span> | <span data-ttu-id="ef3b8-122">Szöveg</span><span class="sxs-lookup"><span data-stu-id="ef3b8-122">Text</span></span> | <span data-ttu-id="ef3b8-123">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-123">The heading for the module.</span></span> |
| <span data-ttu-id="ef3b8-124">A gombostű beállításai: alapértelmezett ikon</span><span class="sxs-lookup"><span data-stu-id="ef3b8-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="ef3b8-125">Kép</span><span class="sxs-lookup"><span data-stu-id="ef3b8-125">Image</span></span> | <span data-ttu-id="ef3b8-126">A térképeken megjelenített üzletekhez használandó gombostű szimbólum képe.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="ef3b8-127">A gombostű beállításai: aktív ikon</span><span class="sxs-lookup"><span data-stu-id="ef3b8-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="ef3b8-128">Kép</span><span class="sxs-lookup"><span data-stu-id="ef3b8-128">Image</span></span> | <span data-ttu-id="ef3b8-129">A térképeken kiválasztott üzlethez használandó gombostű szimbólum képe.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="ef3b8-130">A gombostű beállításai: alapértelmezett ikon színe</span><span class="sxs-lookup"><span data-stu-id="ef3b8-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="ef3b8-131">Karaktersztring</span><span class="sxs-lookup"><span data-stu-id="ef3b8-131">Character string</span></span> | <span data-ttu-id="ef3b8-132">A gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="ef3b8-133">A gombostű beállításai: aktív ikon színe</span><span class="sxs-lookup"><span data-stu-id="ef3b8-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="ef3b8-134">Karaktersztring</span><span class="sxs-lookup"><span data-stu-id="ef3b8-134">Character string</span></span> | <span data-ttu-id="ef3b8-135">A kiválasztott gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="ef3b8-136">Index megjelenítése</span><span class="sxs-lookup"><span data-stu-id="ef3b8-136">Show index</span></span> | <span data-ttu-id="ef3b8-137">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="ef3b8-137">**True** or **False**</span></span> | <span data-ttu-id="ef3b8-138">Ha ez a tulajdonság **Igaz** értékre van állítva, akkor az üzletet jelző összes gombostű szimbóluma egy indexet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="ef3b8-139">Ez az index megegyezik azzal a listanézet-mutatóval, amelyre az üzletválasztó modul mutat.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="ef3b8-140">Engedélyezett leképezési URL-címek hozzáadása a webhely tartalmának biztonsági házirendjéhez</span><span class="sxs-lookup"><span data-stu-id="ef3b8-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="ef3b8-141">Annak érdekében, hogy a térképek modul együttműködjön a Bing Maps szolgáltatással, gondoskodni kell arról, hogy a webhely tartalmának biztonsági házirendjében (CSP) a következő leképezési URL-címeket engedélyezzék (más néven „engedélyezési listához adva”).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="ef3b8-142">Ez a beállítás a Commerce webhelykészítőben végezhető el azzal, ha engedélyezett URL-címeket ad különböző webhely CSP-utasításokhoz (például **img-src**).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="ef3b8-143">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="ef3b8-144">A **connect-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="ef3b8-145">Az **img-src** utasításhoz adja hozzá a **&#42;virtualearth.net** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="ef3b8-146">A **script-src** utasításhoz adja hozzá a **&#42;.bing.com, &#42;.virtualearth.net** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="ef3b8-147">A **script style-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="ef3b8-148">Térképmodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="ef3b8-148">Add a map module to a page</span></span>

<span data-ttu-id="ef3b8-149">A térképmodul oldalon lévő konfigurálásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Üzletválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="ef3b8-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ef3b8-150">Additional resources</span></span>

[<span data-ttu-id="ef3b8-151">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="ef3b8-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ef3b8-152">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="ef3b8-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ef3b8-153">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="ef3b8-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ef3b8-154">Áruházválasztó modul</span><span class="sxs-lookup"><span data-stu-id="ef3b8-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="ef3b8-155">A szervezetéhez tartozó Bing Térképek kezelése</span><span class="sxs-lookup"><span data-stu-id="ef3b8-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="ef3b8-156">8. verziós Bing Maps webes vezérlő</span><span class="sxs-lookup"><span data-stu-id="ef3b8-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
