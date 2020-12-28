---
title: Embléma hozzáadása
description: Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f15680deb0eab763ba68f2897139c915d1f8a6a3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412810"
---
# <a name="add-a-logo"></a><span data-ttu-id="cb446-103">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb446-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cb446-104">Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cb446-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cb446-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cb446-105">Overview</span></span>

<span data-ttu-id="cb446-106">Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez.</span><span class="sxs-lookup"><span data-stu-id="cb446-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="cb446-107">A Dynamics 365 Commerce online modulkönyvtár tartalmaz egy modult ennek a megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb446-107">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="cb446-108">Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="cb446-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="cb446-109">Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót.</span><span class="sxs-lookup"><span data-stu-id="cb446-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="cb446-110">Ez a témakör azonban a leggyakrabban előforduló forgatókönyvet tartalmazza, ahol a logót egy olyan fejléctöredékhez adja hozzá, amely a webhely összes oldalán felhasználható.</span><span class="sxs-lookup"><span data-stu-id="cb446-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb446-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cb446-111">Prerequisites</span></span>

<span data-ttu-id="cb446-112">Mielőtt hozzáadná a logót a webhely összes oldalához, végre kell hajtania ezeket a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="cb446-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="cb446-113">Töltse fel az emblémát a médiatárba.</span><span class="sxs-lookup"><span data-stu-id="cb446-113">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="cb446-114">Fejléctöredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb446-114">Create a header fragment.</span></span> <span data-ttu-id="cb446-115">A töredékek létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Töredékek használata](work-with-fragments.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="cb446-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="cb446-116">Adja meg a fejléctöredéket abban a sablonban, amelyet webhelyének oldalai használnak az elrendezéshez és a modulbeállításokhoz.</span><span class="sxs-lookup"><span data-stu-id="cb446-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="cb446-117">A sablonokkal kapcsolatos további információkért lásd: [Sablonok használata](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cb446-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="cb446-118">Logó hozzáadása a fejléctöredékhez</span><span class="sxs-lookup"><span data-stu-id="cb446-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="cb446-119">A logó hozzáadásához a webhelye fejléctöredékéhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb446-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="cb446-120">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb446-120">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="cb446-121">Válassza ki a létrehozott fejléctöredéket, majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cb446-121">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="cb446-122">Nyissa meg a fejléc modult.</span><span class="sxs-lookup"><span data-stu-id="cb446-122">Expand the header module.</span></span>
1. <span data-ttu-id="cb446-123">A fejléc modul tulajdonságpanelján adjon meg egy képet és egy hivatkozást az emblémát.</span><span class="sxs-lookup"><span data-stu-id="cb446-123">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="cb446-124">Mentse az oldaltöredéket, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="cb446-124">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="cb446-125">A frissített fejléctöredék közzététele után a webhely összes olyan oldala, amely a fejléctöredéket tartalmazó sablont használja, megjeleníti a logót.</span><span class="sxs-lookup"><span data-stu-id="cb446-125">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb446-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cb446-126">Additional resources</span></span>

[<span data-ttu-id="cb446-127">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="cb446-127">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="cb446-128">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="cb446-128">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="cb446-129">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb446-129">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="cb446-130">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb446-130">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="cb446-131">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb446-131">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="cb446-132">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="cb446-132">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="cb446-133">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="cb446-133">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

