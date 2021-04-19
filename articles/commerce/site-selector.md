---
title: Oldalválasztó modul
description: Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6e8eefe7afe385ca77eca6027638ff938e1356e3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791775"
---
# <a name="site-selector-module"></a><span data-ttu-id="8ddd5-103">Telephelyválasztó modul</span><span class="sxs-lookup"><span data-stu-id="8ddd5-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8ddd5-104">Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8ddd5-105">Ha egy vállalatnak különböző webhelyei vannak a különböző piacokon, régiókban és nyelvi területeken, a felhasználóknak egyszerű lehetőséget kell kapniuk a helyek közötti váltásra, hogy kiválaszthassák a preferált vásárlási oldalt.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-105">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="8ddd5-106">Ennek biztosítása érdekében az oldalválasztó modul lehetővé teszi a felhasználók számára a különböző webhelyek böngészését.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-106">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="8ddd5-107">Az oldalválasztó modult be kell állítani azoknak a webhelyeknek (piacoknak, régióknak vagy nyelvi területeknek) a listájára, amelyeket a webhely felhasználói megtekinthetnek.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-107">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddd5-108">Az oldalválasztó modul a Dynamics 365 Commerce 10.0.14-es verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-108">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="8ddd5-109">Az alábbi ábra a webhely fejlécében található oldalválasztó modult mutatja be.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-109">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Példa oldalválasztó modulra a webhely fejlécében](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="8ddd5-111">Az oldalválasztó modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="8ddd5-111">Site selector module properties</span></span>

| <span data-ttu-id="8ddd5-112">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="8ddd5-112">Property name</span></span> | <span data-ttu-id="8ddd5-113">Érték</span><span class="sxs-lookup"><span data-stu-id="8ddd5-113">Value</span></span>                 | <span data-ttu-id="8ddd5-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="8ddd5-114">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="8ddd5-115">Fejléc</span><span class="sxs-lookup"><span data-stu-id="8ddd5-115">Heading</span></span>       | <span data-ttu-id="8ddd5-116">Szöveg</span><span class="sxs-lookup"><span data-stu-id="8ddd5-116">Text</span></span>                  | <span data-ttu-id="8ddd5-117">A modul címe.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-117">The heading for the module.</span></span> |
| <span data-ttu-id="8ddd5-118">Webhelybeállítások</span><span class="sxs-lookup"><span data-stu-id="8ddd5-118">Site options</span></span>  | <span data-ttu-id="8ddd5-119">Név, kép, URL</span><span class="sxs-lookup"><span data-stu-id="8ddd5-119">Name, Image, URL</span></span>      | <span data-ttu-id="8ddd5-120">Ez a tulajdonság megad egy nevet, egy hivatkozást a webhely kezdőlapjára, valamint egy opcionális képet a modulban található minden oldal számára.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-120">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="8ddd5-121">A kép lehet egy zászó, vagy a piac, régió vagy nyelvi terület egyéb ábrázolása.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-121">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="8ddd5-122">Oldalválasztó modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="8ddd5-122">Add a site selector module to a page</span></span>

<span data-ttu-id="8ddd5-123">Az oldalválasztó modul az oldalválasztó helyen adható hozzá a [Fejlécmodulhoz](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="8ddd5-123">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="8ddd5-124">A hozzáadása után megadhatja a modul fejlécét és az oldal beállításait.</span><span class="sxs-lookup"><span data-stu-id="8ddd5-124">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ddd5-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8ddd5-125">Additional resources</span></span>

[<span data-ttu-id="8ddd5-126">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="8ddd5-126">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8ddd5-127">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="8ddd5-127">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8ddd5-128">Útkövetési modul</span><span class="sxs-lookup"><span data-stu-id="8ddd5-128">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="8ddd5-129">Navigációs menü modul</span><span class="sxs-lookup"><span data-stu-id="8ddd5-129">Navigation menu module</span></span>](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]