---
title: A tartalom hozzáadásának módjai
description: Ez a témakör áttekintést nyújt arról, hogy hol és hogyan kell elkezdeni a tartalom kezelését a Microsoft Dynamics 365 Commerce webhelykészítő webfejlesztési eszköztárával.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e6794e528d9fa6066d7246e99a3307bb1bdc9c78
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797575"
---
# <a name="ways-to-add-content"></a><span data-ttu-id="46cde-103">A tartalom hozzáadásának módjai</span><span class="sxs-lookup"><span data-stu-id="46cde-103">Ways to add content</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="46cde-104">Ebben a témakörben áttekintést és dokumentációra mutató hivatkozásokat talál arról, hogyan kezelje a tartalmakat a Microsoft Dynamics 365 Commerce webhelykészítő webfejlesztői eszköztárával.</span><span class="sxs-lookup"><span data-stu-id="46cde-104">This topic provides an overview and links to documentation about how to manage content using the Microsoft Dynamics 365 Commerce site builder web authoring toolset.</span></span>

<span data-ttu-id="46cde-105">A webhely megjelenését, hangulatát és tartalmát sokféleképpen lehet megváltoztatni.</span><span class="sxs-lookup"><span data-stu-id="46cde-105">There are many ways to change the look, feel, and content of your site.</span></span> <span data-ttu-id="46cde-106">A testreszabás előírt szintjétől függően számos ilyen módosítást a nem fejlesztők is végrehajthatnak a webhelykészítővel, a Dynamics 365 Commerce szolgáltatásban található webfejlesztői eszközkészlettel.</span><span class="sxs-lookup"><span data-stu-id="46cde-106">Depending on the required level of customization, many of these changes can be implemented by non-developers within site builder, the web authoring toolset included with Dynamics 365 Commerce.</span></span> <span data-ttu-id="46cde-107">A webhelykészítő segítségével kód írása nélkül készíthet sablonokat, témákat választhat, kiválaszthat és konfirugálhat modulokat.</span><span class="sxs-lookup"><span data-stu-id="46cde-107">Site builder enables you to build templates, select themes, and select and configure modules without writing any code.</span></span> <span data-ttu-id="46cde-108">Ezzel szemben a fejlesztési szakértelem szükséges egy új téma vagy modul létrehozásához, mivel az e-kereskedelem szoftverfejlesztő készlet (SDK) és az Microsoft Dynamics Lifecycle Services (LCS) telepítési munkafolyamatát kell használni.</span><span class="sxs-lookup"><span data-stu-id="46cde-108">By contrast, development skills are required to create a new theme or module, because the e-Commerce software development kit (SDK) and the Microsoft Dynamics Lifecycle Services (LCS) deployment workflow must be used.</span></span>

<span data-ttu-id="46cde-109">A következő témakörök a webhely tartalmának hozzáadásával és kezelésével kapcsolatban jól kezdőpontok lehetnek.</span><span class="sxs-lookup"><span data-stu-id="46cde-109">The following topics are good jumping off points to start understanding how to add and manage site content.</span></span> <span data-ttu-id="46cde-110">A legtöbb felsorolt témakör a webhely azon területeire koncentrálnak, amelyekhez fejlesztők nem szükségesek.</span><span class="sxs-lookup"><span data-stu-id="46cde-110">Most of the topics listed focus on areas of your site that don't require a developer.</span></span> <span data-ttu-id="46cde-111">Néhány az alapvető tartalomszerkesztésről szól, míg mások a webhely rendszergazdai feladataira összpontosítanak.</span><span class="sxs-lookup"><span data-stu-id="46cde-111">Some address basic content editing, while others focus on site administrator tasks.</span></span> <span data-ttu-id="46cde-112">Ezen témák mindegyike olyan specifikus feladatokat mutat be, amelyekhez SDK-munka is szükséges lehet.</span><span class="sxs-lookup"><span data-stu-id="46cde-112">Each of these topics will denote specific tasks might require SDK work.</span></span> <span data-ttu-id="46cde-113">Minden témakör feltételezi, hogy már már létesített egy webhelyet, és hozzáférést kapott a webhelykészírő eszközkészletéhez a webhelye esetén.</span><span class="sxs-lookup"><span data-stu-id="46cde-113">Each topic assumes that you have already provisioned a site and been granted access to the site builder toolset for your site.</span></span>

<span data-ttu-id="46cde-114">Válassza ki az alábbi témakörök egyikét az elinduláshoz.</span><span class="sxs-lookup"><span data-stu-id="46cde-114">Select one of the following topics to get started.</span></span>

- <span data-ttu-id="46cde-115">Ha szeretné megismerni a webhelykészítőben és a dokumentációjában használt tartalomkezelési terminológiát, tekintse meg az [Oldalmodell szószedete](page-elements-overview.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="46cde-115">To familiarize yourself with the content management terminology used in site builder and within this documentation, see [Page model glossary](page-elements-overview.md).</span></span>
- <span data-ttu-id="46cde-116">A modulok tartalomkezelési munkafolyamatok keretében történő működésének megértéséhez lásd: [Modulok használata](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-116">To understand how modules work within content management workflows, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="46cde-117">Ha módosítani szeretné a szöveget, képeket vagy videót egy létező webhely oldalán, tanulmányozza a következő témakört: [Modulok használata](work-with-modules.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-117">To change the text, images, or video on an existing site page, see [Work with modules](work-with-modules.md).</span></span>
- <span data-ttu-id="46cde-118">Ha szeretné megtudni, hogy a töredékek hogyan tehetik a tartalomkezelést hatékonyabbá és rugalmasabbá, tekintse meg: [Töredékek használata](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-118">To see how fragments can make content management more efficient and flexible, see [Work with fragments](work-with-fragments.md).</span></span>
- <span data-ttu-id="46cde-119">Ha szeretné biztosítani, hogy a webes tartalomfejlesztőknek sikeres, márkának megfelelő fejlesztői élményben lesz része, tekintse meg a következőket: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md) és [Sablonok használata](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-119">To help ensure a successful on-brand authoring experience for web content authors, see [Templates and layouts overview](templates-layouts-overview.md) and [Work with templates](work-with-templates.md).</span></span>
- <span data-ttu-id="46cde-120">A webhely szakaszainak átrendezéséhez lásd: [Elrendezések használata](work-with-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-120">To rearrange sections on a site page, see [Work with layouts](work-with-layouts.md).</span></span>
- <span data-ttu-id="46cde-121">A webhelyoldalak betűtípusának, színeinek és általános megjelenésének módosításához lásd: [Webhelytéma kiválasztása](select-site-theme.md) vagy [A CSS felülbírálási fájlok használata](css-override-files.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-121">To change the fonts, colors, and general look of site pages, see [Select a site theme](select-site-theme.md) or [Work with CSS over-ride files](css-override-files.md).</span></span>
- <span data-ttu-id="46cde-122">Új navigációs lehetőségek átrendezéséhez vagy hozzáadásához lásd: [Webhelynavigáció testreszabása](customize-site-navigation.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-122">To rearrange or add new navigation options, see [Customize site navigation](customize-site-navigation.md).</span></span>
- <span data-ttu-id="46cde-123">Egyidejű webtartalom-változások széles körének előkészítésével, előnézetének megtekintésével és közzétételével kapcsolatos információkért lásd: [Közzétételi csoportok használata](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="46cde-123">To learn how to stage, preview, and publish a broad set of concurrent web content changes, see [Work with publish groups](publish-groups.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46cde-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="46cde-124">Additional resources</span></span>

[<span data-ttu-id="46cde-125">Szerkesztési oldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="46cde-125">Authoring page overview</span></span>](authoring-home-overview.md)

[<span data-ttu-id="46cde-126">Oldal modellszószedete</span><span class="sxs-lookup"><span data-stu-id="46cde-126">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="46cde-127">Állapotok és életciklus-dokumentálás</span><span class="sxs-lookup"><span data-stu-id="46cde-127">Document states and lifecycle</span></span>](document-states-overview.md)

[<span data-ttu-id="46cde-128">Csatornaközi megosztás engedélyezése és használata</span><span class="sxs-lookup"><span data-stu-id="46cde-128">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
