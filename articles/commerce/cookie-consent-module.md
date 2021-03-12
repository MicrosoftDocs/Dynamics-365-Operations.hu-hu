---
title: Cookie-hozzájárulás modul
description: Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 504232285267fb3663093a84a371e0040233ce23
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993525"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="34345-103">Cookie-hozzájárulás modul</span><span class="sxs-lookup"><span data-stu-id="34345-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="34345-104">Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="34345-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="34345-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="34345-105">Overview</span></span>

<span data-ttu-id="34345-106">A cookie-hozzájárulás modul felkéri a webhely felhasználóit, hogy explicit módon egyezzenek a bele a cookie-k engedélyezéséve bármely funkcióhoz vagy modulhoz, amely nyomon követi a böngésző-cookie-kat.</span><span class="sxs-lookup"><span data-stu-id="34345-106">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="34345-107">A hozzájárulás megadása szükséges az első alkalommal, amikor a webhely felhasználója egy új böngésző-munkamenetben böngészik a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="34345-107">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="34345-108">A jóváhagyás megkapását követően az nyomon lesz követve, és nem lesz újra beleegyezés kérve a webhely felhasználójától.</span><span class="sxs-lookup"><span data-stu-id="34345-108">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="34345-109">További információ:- [Cookie-k megfelelősége](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="34345-109">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="34345-110">Ha nem érkezik meg a webhely felhasználójának cookie-hozzájárulása, akkor a program nem jeleníti meg a cookie-hozzájárulást igénylő funkciókat és modulokat a lapon.</span><span class="sxs-lookup"><span data-stu-id="34345-110">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="34345-111">Például a pénztár modul, a közösségi megosztás modul és az előnyben részesített áruház funkció megköveteli a cookie-hozzájárulást, és nem fog megjelenni, ha a webhely felhasználójának hozzájárulása nem érkezik meg.</span><span class="sxs-lookup"><span data-stu-id="34345-111">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="34345-112">A cookie-hozzájárulási modul konfigurálható a lap fejléctöredékében, hogy az a lap betöltésekor érvényesíthető legyen.</span><span class="sxs-lookup"><span data-stu-id="34345-112">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="34345-113">A cookie-hozzájárulási modulnak tartalmaznia kell egy olyan egyértelmű üzenetet, amely tájékoztatja a webhely felhasználóját a webhely cookie-használatáról, és tartalmaznia kell egy hivatkozást webhely adatvédelmi lapjára.</span><span class="sxs-lookup"><span data-stu-id="34345-113">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="34345-114">A következő ábra a webhely fejlécében megjelenő cookie-hozzájárulási üzenetet jelenít meg, egy hivatkozással az adatvédelmi tájékoztató oldalra.</span><span class="sxs-lookup"><span data-stu-id="34345-114">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="34345-115">![Példa egy cookie-hozzájárulási modulra](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="34345-115">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="34345-116">Cookie-hozzájárulási modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="34345-116">Cookie consent module properties</span></span>

| <span data-ttu-id="34345-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="34345-117">Property name</span></span>             | <span data-ttu-id="34345-118">Érték</span><span class="sxs-lookup"><span data-stu-id="34345-118">Value</span></span>                 | <span data-ttu-id="34345-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="34345-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="34345-120">Rich Text</span><span class="sxs-lookup"><span data-stu-id="34345-120">Rich Text</span></span>                  | <span data-ttu-id="34345-121">Rich Text</span><span class="sxs-lookup"><span data-stu-id="34345-121">Rich Text</span></span> | <span data-ttu-id="34345-122">Egy Rich Text értesítést határoz meg a webhely felhasználói számára arról, hogy a webhely böngésző cookie-kat használ, és a felhasználóknak el kell fogadniuk a cookie-k használatát a webhely teljes funkcionalitásához.</span><span class="sxs-lookup"><span data-stu-id="34345-122">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="34345-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="34345-123">Links</span></span> | <span data-ttu-id="34345-124">URL-cím</span><span class="sxs-lookup"><span data-stu-id="34345-124">URL</span></span> | <span data-ttu-id="34345-125">Egy vagy több hivatkozás hozzáadható a webhely adatvédelmi lapjára, amely leírja, hogy milyen típusú cookie-k vannak nyomon követve a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="34345-125">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="34345-126">Cookie-hozzájárulási modul hozzáadása a webhely oldalaihoz</span><span class="sxs-lookup"><span data-stu-id="34345-126">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="34345-127">A cookie-hozzájárulási modul több oldalra történő hatékony hozzáadásához hozzáadhatók egy megosztott lapfejléc-töredékhez is.</span><span class="sxs-lookup"><span data-stu-id="34345-127">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="34345-128">Miután a fejléc-töredéket hozzáadta az összes webhelyoldalhoz, a program automatikusan megjeleníti a cookie-hozzájárulást, amikor a webhely felhasználója első alkalommal a webhely valamelyik lapjára navigál.</span><span class="sxs-lookup"><span data-stu-id="34345-128">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="34345-129">További tájékoztatás a fejléc-töredékekről és modulokról: [Fejléc modul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="34345-129">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34345-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="34345-130">Additional resources</span></span>

[<span data-ttu-id="34345-131">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="34345-131">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="34345-132">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="34345-132">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="34345-133">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="34345-133">Cookie compliance</span></span>](cookie-compliance.md)
