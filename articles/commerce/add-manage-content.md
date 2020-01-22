---
title: A tartalom hozzáadásának módjai
description: Ez a témakör az Ön Microsoft Dynamics 365 Commerce-webhelyén található tartalom hozzáadásával és kezelésével kapcsolatban tartalmaz tájékoztatást.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
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
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2232dc7cdd24416b0df0919b96cd5d1f8113299f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914654"
---
# <a name="ways-to-add-content"></a><span data-ttu-id="4b298-103">A tartalom hozzáadásának módjai</span><span class="sxs-lookup"><span data-stu-id="4b298-103">Ways to add content</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4b298-104">Ez a témakör az Ön Microsoft Dynamics 365 Commerce-webhelyén található tartalom hozzáadásával és kezelésével kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="4b298-104">This topic provides information about how to add and manage content on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="4b298-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="4b298-105">Overview</span></span>

<span data-ttu-id="4b298-106">A webhely megjelenését, hangulatát és tartalmát sokféleképpen lehet megváltoztatni.</span><span class="sxs-lookup"><span data-stu-id="4b298-106">There are many ways to change the look, feel, and content of your site.</span></span> <span data-ttu-id="4b298-107">A testreszabáshoz szükséges szinttől függően számos ilyen módosításvégrehajtására nem fejlesztők is képesek.</span><span class="sxs-lookup"><span data-stu-id="4b298-107">Depending on the required level of customization, many of these changes can be implemented by non-developers.</span></span> <span data-ttu-id="4b298-108">Például nem kell kódot írni a sablonok létrehozásához, a témák kiválasztásához, a modulok kiválasztásához és konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="4b298-108">For example, no code has to be written to build templates, select themes, and select and configure modules.</span></span> <span data-ttu-id="4b298-109">Ezzel szemben a fejlesztési szakértelem szükséges egy új téma vagy modul létrehozásához, mivel az e-kereskedelem szoftverfejlesztő készlet (SDK) és az Microsoft Dynamics Lifecycle Services (LCS) telepítési munkafolyamatát kell használni.</span><span class="sxs-lookup"><span data-stu-id="4b298-109">By contrast, development skills are required to create a new theme or module, because the e-Commerce software development kit (SDK) and the Microsoft Dynamics Lifecycle Services (LCS) deployment workflow must be used.</span></span>

<span data-ttu-id="4b298-110">A következő témakör a tartalom hozzáadásával és kezelésével kapcsolatban tartalmaz részletes tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="4b298-110">The following topics provide detailed information about how to add and manage site content.</span></span> <span data-ttu-id="4b298-111">A webhely azon területeire koncentrálnak, amelyekhez fejlesztők nem szükségesek.</span><span class="sxs-lookup"><span data-stu-id="4b298-111">They focus on areas of your site that don't require a developer.</span></span> <span data-ttu-id="4b298-112">Szükség szerint rámutatnak az SDK-munkát igénylő feladatokra.</span><span class="sxs-lookup"><span data-stu-id="4b298-112">As required, they point out tasks that require SDK work.</span></span>

- <span data-ttu-id="4b298-113">Ha módosítani szeretné a szöveget, képeket vagy videót egy létező webhely oldalán, tanulmányozza a következő témakört: [Modulok használata](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="4b298-113">To change the text, images, or video on an existing site page, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="4b298-114">Annak érdekében, hogy a webtartalom-szerkesztők számára egyszerűen használható, márkához illő szerkesztői élményt tegyen lehetővé, tekintse meg a [Sablonok használata](work-with-templates.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="4b298-114">To help guarantee a foolproof, on-brand authoring experience for web content authors, see [Work with templates](work-with-templates.md).</span></span>
- <span data-ttu-id="4b298-115">A webhely szakaszainak átrendezéséhez lásd: [Elrendezések használata](work-with-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="4b298-115">To rearrange sections on a site page, see [Work with layouts](work-with-layouts.md).</span></span>
- <span data-ttu-id="4b298-116">A webhelyoldalak betűtípusának, színeinek és általános megjelenésének módosításához lásd: [Webhelytéma kiválasztása](select-site-theme.md).</span><span class="sxs-lookup"><span data-stu-id="4b298-116">To change the fonts, colors, and general look of site pages, see [Select a site theme](select-site-theme.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b298-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4b298-117">Additional resources</span></span>

[<span data-ttu-id="4b298-118">Oldal modellszószedete</span><span class="sxs-lookup"><span data-stu-id="4b298-118">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="4b298-119">Állapotok és életciklus-dokumentálás</span><span class="sxs-lookup"><span data-stu-id="4b298-119">Document states and lifecycle</span></span>](document-states-overview.md)

[<span data-ttu-id="4b298-120">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="4b298-120">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="4b298-121">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="4b298-121">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="4b298-122">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="4b298-122">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="4b298-123">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="4b298-123">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="4b298-124">Webhely-navigáció testreszabása</span><span class="sxs-lookup"><span data-stu-id="4b298-124">Customize site navigation</span></span>](customize-site-navigation.md)
