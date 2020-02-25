---
title: A tartalom hozzáadásának módjai
description: Ez a témakör áttekintést nyújt arról, hogy hol és hogyan kell elkezdeni a tartalom kezelését a Microsoft Dynamics 365 Commerce webhelykészítő webfejlesztési eszköztárával.
author: phinneyridge
manager: annbe
ms.date: 01/31/2020
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
ms.openlocfilehash: 916e28c2628613332246d19af0fae81f258404b0
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025725"
---
# <a name="ways-to-add-content"></a><span data-ttu-id="c160d-103">A tartalom hozzáadásának módjai</span><span class="sxs-lookup"><span data-stu-id="c160d-103">Ways to add content</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c160d-104">Ebben a témakörben áttekintést és dokumentációra mutató hivatkozásokat talál arról, hogyan kezelje a tartalmakat a Microsoft Dynamics 365 Commerce webhelykészítő webfejlesztői eszköztárával.</span><span class="sxs-lookup"><span data-stu-id="c160d-104">This topic provides an overview and links to documentation about how to manage content using the Microsoft Dynamics 365 Commerce site builder web authoring toolset.</span></span>

## <a name="overview"></a><span data-ttu-id="c160d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c160d-105">Overview</span></span>

<span data-ttu-id="c160d-106">A webhely megjelenését, hangulatát és tartalmát sokféleképpen lehet megváltoztatni.</span><span class="sxs-lookup"><span data-stu-id="c160d-106">There are many ways to change the look, feel, and content of your site.</span></span> <span data-ttu-id="c160d-107">A testreszabás előírt szintjétől függően számos ilyen módosítást a nem fejlesztők is végrehajthatnak a webhelykészítővel, a Dynamics 365 Commerce szolgáltatásban található webfejlesztői eszközkészlettel.</span><span class="sxs-lookup"><span data-stu-id="c160d-107">Depending on the required level of customization, many of these changes can be implemented by non-developers within site builder, the web authoring toolset included with Dynamics 365 Commerce.</span></span> <span data-ttu-id="c160d-108">A webhelykészítő segítségével kód írása nélkül készíthet sablonokat, témákat választhat, kiválaszthat és konfirugálhat modulokat.</span><span class="sxs-lookup"><span data-stu-id="c160d-108">Site builder enables you to build templates, select themes, and select and configure modules without writing any code.</span></span> <span data-ttu-id="c160d-109">Ezzel szemben a fejlesztési szakértelem szükséges egy új téma vagy modul létrehozásához, mivel az e-kereskedelem szoftverfejlesztő készlet (SDK) és az Microsoft Dynamics Lifecycle Services (LCS) telepítési munkafolyamatát kell használni.</span><span class="sxs-lookup"><span data-stu-id="c160d-109">By contrast, development skills are required to create a new theme or module, because the e-Commerce software development kit (SDK) and the Microsoft Dynamics Lifecycle Services (LCS) deployment workflow must be used.</span></span>

<span data-ttu-id="c160d-110">A következő témakörök a webhely tartalmának hozzáadásával és kezelésével kapcsolatban jól kezdőpontok lehetnek.</span><span class="sxs-lookup"><span data-stu-id="c160d-110">The following topics are good jumping off points to start understanding how to add and manage site content.</span></span> <span data-ttu-id="c160d-111">A legtöbb felsorolt témakör a webhely azon területeire koncentrálnak, amelyekhez fejlesztők nem szükségesek.</span><span class="sxs-lookup"><span data-stu-id="c160d-111">Most of the topics listed focus on areas of your site that don't require a developer.</span></span> <span data-ttu-id="c160d-112">Néhány az alapvető tartalomszerkesztésről szól, míg mások a webhely rendszergazdai feladataira összpontosítanak.</span><span class="sxs-lookup"><span data-stu-id="c160d-112">Some address basic content editing, while others focus on site administrator tasks.</span></span> <span data-ttu-id="c160d-113">Ezen témák mindegyike olyan specifikus feladatokat mutat be, amelyekhez SDK-munka is szükséges lehet.</span><span class="sxs-lookup"><span data-stu-id="c160d-113">Each of these topics will denote specific tasks might require SDK work.</span></span> <span data-ttu-id="c160d-114">Minden témakör feltételezi, hogy már már létesített egy webhelyet, és hozzáférést kapott a webhelykészírő eszközkészletéhez a webhelye esetén.</span><span class="sxs-lookup"><span data-stu-id="c160d-114">Each topic assumes that you have already provisioned a site and been granted access to the site builder toolset for your site.</span></span>

<span data-ttu-id="c160d-115">Válassza ki az alábbi témakörök egyikét az elinduláshoz.</span><span class="sxs-lookup"><span data-stu-id="c160d-115">Select one of the following topics to get started.</span></span>

- <span data-ttu-id="c160d-116">Ha szeretné megismerni a webhelykészítőben és a dokumentációjában használt tartalomkezelési terminológiát, tekintse meg az [Oldalmodell szószedete](page-elements-overview.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="c160d-116">To familiarize yourself with the content management terminology used in site builder and within this documentation, see [Page model glossary](page-elements-overview.md).</span></span>
- <span data-ttu-id="c160d-117">A modulok tartalomkezelési munkafolyamatok keretében történő működésének megértéséhez lásd: [Modulok használata](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-117">To understand how modules work within content management workflows, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="c160d-118">Ha módosítani szeretné a szöveget, képeket vagy videót egy létező webhely oldalán, tanulmányozza a következő témakört: [Modulok használata](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-118">To change the text, images, or video on an existing site page, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="c160d-119">Ha szeretné megtudni, hogy a töredékek hogyan tehetik a tartalomkezelést hatékonyabbá és rugalmasabbá, tekintse meg: [Töredékek használata](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-119">To see how fragments can make content management more efficient and flexible, see [Work with fragments](work-with-fragments.md).</span></span>
- <span data-ttu-id="c160d-120">Ha szeretné biztosítani, hogy a webes tartalomfejlesztőknek sikeres, márkának megfelelő fejlesztői élményben lesz része, tekintse meg a következőket: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md) és [Sablonok használata](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-120">To help ensure a successful on-brand authoring experience for web content authors, see [Templates and layouts overview](templates-layouts-overview.md) and [Work with templates](work-with-templates.md).</span></span>
- <span data-ttu-id="c160d-121">A webhely szakaszainak átrendezéséhez lásd: [Elrendezések használata](work-with-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-121">To rearrange sections on a site page, see [Work with layouts](work-with-layouts.md).</span></span>
- <span data-ttu-id="c160d-122">A webhelyoldalak betűtípusának, színeinek és általános megjelenésének módosításához lásd: [Webhelytéma kiválasztása](select-site-theme.md) vagy [A CSS felülbírálási fájlok használata](css-override-files.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-122">To change the fonts, colors, and general look of site pages, see [Select a site theme](select-site-theme.md) or [Work with CSS over-ride files](css-override-files.md).</span></span>
- <span data-ttu-id="c160d-123">Új navigációs lehetőségek átrendezéséhez vagy hozzáadásához lásd: [Webhelynavigáció testreszabása](customize-site-navigation.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-123">To rearrange or add new navigation options, see [Customize site navigation](customize-site-navigation.md).</span></span>
- <span data-ttu-id="c160d-124">Egyidejű webtartalom-változások széles körének előkészítésével, előnézetének megtekintésével és közzétételével kapcsolatos információkért lásd: [Közzétételi csoportok használata](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c160d-124">To learn how to stage, preview, and publish a broad set of concurrent web content changes, see [Work with publish groups](publish-groups.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c160d-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c160d-125">Additional resources</span></span>

[<span data-ttu-id="c160d-126">Szerkesztési oldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="c160d-126">Authoring page overview</span></span>](authoring-home-overview.md)

[<span data-ttu-id="c160d-127">Állapotok és életciklus-dokumentálás</span><span class="sxs-lookup"><span data-stu-id="c160d-127">Document states and lifecycle</span></span>](document-states-overview.md)
