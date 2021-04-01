---
title: Modul feltérképezése
description: Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 74991a2979540dab344f39976005250637fab29c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252582"
---
# <a name="map-module"></a><span data-ttu-id="8cb2b-103">Térképmodul</span><span class="sxs-lookup"><span data-stu-id="8cb2b-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="8cb2b-104">Ez a témakör a feltérképezési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket konfigurálni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8cb2b-105">A modul feltérképezése egy interaktív térképen jeleníti meg az üzleteket, amelyeket a [8. verziós Bing Térképek webes vezérlő](https://docs.microsoft.com/bingmaps/v8-web-control/) használatával renderelnek.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-105">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="8cb2b-106">A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce központ megosztott paraméterei oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-106">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="8cb2b-107">A modul feltérképezése különböző nézeteket nyújt – például közúti, légi és utcai –, amelyekkel a felhasználók megtekinthetik a leképezési helyeket.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-107">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="8cb2b-108">Olyan interakciókat is lehetővé tesznek, mint például a nagyítás és a felhasználó helyének használata.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-108">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="8cb2b-109">A modul feltérképezése az üzletválasztó modullal együtt dolgozik a térképeken megjelenített üzletek földrajzi helyeinek meghatározásában.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-109">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="8cb2b-110">Az üzletválasztó és a modul feltérképezések akkor lépnek interakcióba, ha a felhasználó a webhely egyik moduljában kiválaszt egy üzletet.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-110">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="8cb2b-111">A modul feltérképezések az üzletválasztó modulokkal való interakción túl más forgatókönyvek esetén is kiterjeszthetőek.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-111">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="8cb2b-112">Azonban a modul testreszabása kötelező.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-112">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="8cb2b-113">Az térkép modul a Dynamics 365 Commerce 10.0.13-as verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-113">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="8cb2b-114">A következő kép egy üzlet oldalán használt letérképezési modul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-114">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Példa egy üzletválasztó modulra](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="8cb2b-116">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="8cb2b-116">Module properties</span></span>

| <span data-ttu-id="8cb2b-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="8cb2b-117">Property name</span></span>             | <span data-ttu-id="8cb2b-118">Érték</span><span class="sxs-lookup"><span data-stu-id="8cb2b-118">Value</span></span>                 | <span data-ttu-id="8cb2b-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="8cb2b-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="8cb2b-120">Címsor</span><span class="sxs-lookup"><span data-stu-id="8cb2b-120">Heading</span></span> | <span data-ttu-id="8cb2b-121">Szöveg</span><span class="sxs-lookup"><span data-stu-id="8cb2b-121">Text</span></span> | <span data-ttu-id="8cb2b-122">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-122">The heading for the module.</span></span> |
| <span data-ttu-id="8cb2b-123">A gombostű beállításai: alapértelmezett ikon</span><span class="sxs-lookup"><span data-stu-id="8cb2b-123">Pushpin options: Default icon</span></span> | <span data-ttu-id="8cb2b-124">Kép</span><span class="sxs-lookup"><span data-stu-id="8cb2b-124">Image</span></span> | <span data-ttu-id="8cb2b-125">A térképeken megjelenített üzletekhez használandó gombostű szimbólum képe.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-125">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="8cb2b-126">A gombostű beállításai: aktív ikon</span><span class="sxs-lookup"><span data-stu-id="8cb2b-126">Pushpin options: Active icon</span></span> | <span data-ttu-id="8cb2b-127">Kép</span><span class="sxs-lookup"><span data-stu-id="8cb2b-127">Image</span></span> | <span data-ttu-id="8cb2b-128">A térképeken kiválasztott üzlethez használandó gombostű szimbólum képe.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-128">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="8cb2b-129">A gombostű beállításai: alapértelmezett ikon színe</span><span class="sxs-lookup"><span data-stu-id="8cb2b-129">Pushpin options: Default icon color</span></span> | <span data-ttu-id="8cb2b-130">Karaktersztring</span><span class="sxs-lookup"><span data-stu-id="8cb2b-130">Character string</span></span> | <span data-ttu-id="8cb2b-131">A gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-131">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="8cb2b-132">A gombostű beállításai: aktív ikon színe</span><span class="sxs-lookup"><span data-stu-id="8cb2b-132">Pushpin options: Active icon color</span></span> | <span data-ttu-id="8cb2b-133">Karaktersztring</span><span class="sxs-lookup"><span data-stu-id="8cb2b-133">Character string</span></span> | <span data-ttu-id="8cb2b-134">A kiválasztott gombostű szimbólumok színének szöveges vagy hexadecimális értékének beállítása a térképen.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-134">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="8cb2b-135">Index megjelenítése</span><span class="sxs-lookup"><span data-stu-id="8cb2b-135">Show index</span></span> | <span data-ttu-id="8cb2b-136">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="8cb2b-136">**True** or **False**</span></span> | <span data-ttu-id="8cb2b-137">Ha ez a tulajdonság **Igaz** értékre van állítva, akkor az üzletet jelző összes gombostű szimbóluma egy indexet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-137">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="8cb2b-138">Ez az index megegyezik azzal a listanézet-mutatóval, amelyre az üzletválasztó modul mutat.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-138">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="8cb2b-139">Engedélyezett leképezési URL-címek hozzáadása a webhely tartalmának biztonsági házirendjéhez</span><span class="sxs-lookup"><span data-stu-id="8cb2b-139">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="8cb2b-140">Annak érdekében, hogy a térképek modul együttműködjön a Bing Térképek szolgáltatással, gondoskodni kell arról, hogy a webhely tartalmának biztonsági házirendjében (CSP) a következő leképezési URL-címeket engedélyezzék.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-140">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed per your site's content security policy (CSP).</span></span> <span data-ttu-id="8cb2b-141">Ez a beállítás a Commerce webhelykészítőben végezhető el azzal, ha engedélyezett URL-címeket ad különböző webhely CSP-utasításokhoz (például **img-src**).</span><span class="sxs-lookup"><span data-stu-id="8cb2b-141">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="8cb2b-142">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8cb2b-142">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="8cb2b-143">A **connect-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-143">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="8cb2b-144">Az **img-src** utasításhoz adja hozzá a **&#42;virtualearth.net** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-144">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="8cb2b-145">A **script-src** utasításhoz adja hozzá a **&#42;.bing.com, &#42;.virtualearth.net** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-145">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="8cb2b-146">A **script style-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="8cb2b-146">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="8cb2b-147">Térképmodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="8cb2b-147">Add a map module to a page</span></span>

<span data-ttu-id="8cb2b-148">A térképmodul oldalon lévő konfigurálásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Üzletválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="8cb2b-148">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="8cb2b-149">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8cb2b-149">Additional resources</span></span>

[<span data-ttu-id="8cb2b-150">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="8cb2b-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8cb2b-151">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="8cb2b-151">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8cb2b-152">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="8cb2b-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8cb2b-153">Üzletválasztó modul</span><span class="sxs-lookup"><span data-stu-id="8cb2b-153">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="8cb2b-154">A szervezetéhez tartozó Bing Térképek kezelése</span><span class="sxs-lookup"><span data-stu-id="8cb2b-154">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="8cb2b-155">8. verziós Bing Maps webes vezérlő</span><span class="sxs-lookup"><span data-stu-id="8cb2b-155">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]