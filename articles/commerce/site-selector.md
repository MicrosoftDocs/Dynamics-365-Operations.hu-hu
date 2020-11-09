---
title: Oldalválasztó modul
description: Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.openlocfilehash: bd54695f54b501631f916328c05bfd47e538d50d
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055830"
---
# <a name="site-selector-module"></a><span data-ttu-id="35267-103">Oldalválasztó modul</span><span class="sxs-lookup"><span data-stu-id="35267-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="35267-104">Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="35267-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="35267-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="35267-105">Overview</span></span>

<span data-ttu-id="35267-106">Ha egy vállalatnak különböző webhelyei vannak a különböző piacokon, régiókban és nyelvi területeken, a felhasználóknak egyszerű lehetőséget kell kapniuk a helyek közötti váltásra, hogy kiválaszthassák a preferált vásárlási oldalt.</span><span class="sxs-lookup"><span data-stu-id="35267-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="35267-107">Ennek biztosítása érdekében az oldalválasztó modul lehetővé teszi a felhasználók számára a különböző webhelyek böngészését.</span><span class="sxs-lookup"><span data-stu-id="35267-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="35267-108">Az oldalválasztó modult be kell állítani azoknak a webhelyeknek (piacoknak, régióknak vagy nyelvi területeknek) a listájára, amelyeket a webhely felhasználói megtekinthetnek.</span><span class="sxs-lookup"><span data-stu-id="35267-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="35267-109">Az oldalválasztó modul a Dynamics 365 Commerce 10.0.14-es verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="35267-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="35267-110">Az alábbi ábra a webhely fejlécében található oldalválasztó modult mutatja be.</span><span class="sxs-lookup"><span data-stu-id="35267-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Példa oldalválasztó modulra a webhely fejlécében](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="35267-112">Az oldalválasztó modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="35267-112">Site selector module properties</span></span>

| <span data-ttu-id="35267-113">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="35267-113">Property name</span></span> | <span data-ttu-id="35267-114">Érték</span><span class="sxs-lookup"><span data-stu-id="35267-114">Value</span></span>                 | <span data-ttu-id="35267-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="35267-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="35267-116">Fejléc</span><span class="sxs-lookup"><span data-stu-id="35267-116">Heading</span></span>       | <span data-ttu-id="35267-117">Szöveg</span><span class="sxs-lookup"><span data-stu-id="35267-117">Text</span></span>                  | <span data-ttu-id="35267-118">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="35267-118">The heading for the module.</span></span> |
| <span data-ttu-id="35267-119">Webhelybeállítások</span><span class="sxs-lookup"><span data-stu-id="35267-119">Site options</span></span>  | <span data-ttu-id="35267-120">Név, kép, URL</span><span class="sxs-lookup"><span data-stu-id="35267-120">Name, Image, URL</span></span>      | <span data-ttu-id="35267-121">Ez a tulajdonság megad egy nevet, egy hivatkozást a webhely kezdőlapjára, valamint egy opcionális képet a modulban található minden oldal számára.</span><span class="sxs-lookup"><span data-stu-id="35267-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="35267-122">A kép lehet egy zászó, vagy a piac, régió vagy nyelvi terület egyéb ábrázolása.</span><span class="sxs-lookup"><span data-stu-id="35267-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="35267-123">Oldalválasztó modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="35267-123">Add a site selector module to a page</span></span>

<span data-ttu-id="35267-124">Az oldalválasztó modul az oldalválasztó helyen adható hozzá a [Fejlécmodulhoz](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="35267-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="35267-125">A hozzáadása után megadhatja a modul fejlécét és az oldal beállításait.</span><span class="sxs-lookup"><span data-stu-id="35267-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35267-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="35267-126">Additional resources</span></span>

[<span data-ttu-id="35267-127">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="35267-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="35267-128">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="35267-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="35267-129">Útkövetési modul</span><span class="sxs-lookup"><span data-stu-id="35267-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="35267-130">Navigációs menü modul</span><span class="sxs-lookup"><span data-stu-id="35267-130">Navigation menu module</span></span>](nav-menu-module.md)
