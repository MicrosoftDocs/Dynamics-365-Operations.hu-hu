---
title: Embléma hozzáadása
description: Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797599"
---
# <a name="add-a-logo"></a><span data-ttu-id="a5820-103">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a5820-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5820-104">Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a5820-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a5820-105">Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez.</span><span class="sxs-lookup"><span data-stu-id="a5820-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="a5820-106">A Dynamics 365 Commerce online modulkönyvtár tartalmaz egy modult ennek a megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a5820-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="a5820-107">Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="a5820-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="a5820-108">Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót.</span><span class="sxs-lookup"><span data-stu-id="a5820-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="a5820-109">Ez a témakör azonban a leggyakrabban előforduló forgatókönyvet tartalmazza, ahol a logót egy olyan fejléctöredékhez adja hozzá, amely a webhely összes oldalán felhasználható.</span><span class="sxs-lookup"><span data-stu-id="a5820-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5820-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a5820-110">Prerequisites</span></span>

<span data-ttu-id="a5820-111">Mielőtt hozzáadná a logót a webhely összes oldalához, végre kell hajtania ezeket a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="a5820-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="a5820-112">Töltse fel az emblémát a médiatárba.</span><span class="sxs-lookup"><span data-stu-id="a5820-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="a5820-113">Fejléctöredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="a5820-113">Create a header fragment.</span></span> <span data-ttu-id="a5820-114">A töredékek létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Töredékek használata](work-with-fragments.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="a5820-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="a5820-115">Adja meg a fejléctöredéket abban a sablonban, amelyet webhelyének oldalai használnak az elrendezéshez és a modulbeállításokhoz.</span><span class="sxs-lookup"><span data-stu-id="a5820-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="a5820-116">A sablonokkal kapcsolatos további információkért lásd: [Sablonok használata](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a5820-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="a5820-117">Logó hozzáadása a fejléctöredékhez</span><span class="sxs-lookup"><span data-stu-id="a5820-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="a5820-118">A logó hozzáadásához a webhelye fejléctöredékéhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a5820-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="a5820-119">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a5820-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="a5820-120">Válassza ki a létrehozott fejléctöredéket, majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a5820-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="a5820-121">Nyissa meg a fejléc modult.</span><span class="sxs-lookup"><span data-stu-id="a5820-121">Expand the header module.</span></span>
1. <span data-ttu-id="a5820-122">A fejléc modul tulajdonságpanelján adjon meg egy képet és egy hivatkozást az emblémát.</span><span class="sxs-lookup"><span data-stu-id="a5820-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="a5820-123">Mentse az oldaltöredéket, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="a5820-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="a5820-124">A frissített fejléctöredék közzététele után a webhely összes olyan oldala, amely a fejléctöredéket tartalmazó sablont használja, megjeleníti a logót.</span><span class="sxs-lookup"><span data-stu-id="a5820-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5820-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a5820-125">Additional resources</span></span>

[<span data-ttu-id="a5820-126">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a5820-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="a5820-127">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="a5820-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="a5820-128">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a5820-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="a5820-129">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a5820-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="a5820-130">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a5820-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="a5820-131">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="a5820-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="a5820-132">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="a5820-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
