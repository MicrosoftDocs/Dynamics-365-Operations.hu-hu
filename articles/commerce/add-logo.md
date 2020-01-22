---
title: Embléma hozzáadása
description: Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
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
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914621"
---
# <a name="add-a-logo"></a><span data-ttu-id="52e63-103">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="52e63-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="52e63-104">Ez a témakör azt mutatja be, hogyan adhat hozzá logót a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="52e63-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="52e63-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="52e63-105">Overview</span></span>

<span data-ttu-id="52e63-106">Amikor felépíti a webhelyét, valószínűleg az első dolgai egyike lesz hozzáadni a vállalata vagy márkája logóját a webhely fejlécéhez.</span><span class="sxs-lookup"><span data-stu-id="52e63-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="52e63-107">A Dynamics 365 Commerce online kezdőszett tartalmaz egy modult ennek a megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="52e63-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="52e63-108">Hozzáadhat egy logót közvetlenül egy sablonhoz, elrendezéshez vagy oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="52e63-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="52e63-109">Így egyszerűen módosíthatja az adott oldalakon vagy oldalcsoportokon megjelenő logót.</span><span class="sxs-lookup"><span data-stu-id="52e63-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="52e63-110">Ez a témakör azonban a leggyakrabban előforduló forgatókönyvet tartalmazza, ahol a logót egy olyan fejléctöredékhez adja hozzá, amely a webhely összes oldalán felhasználható.</span><span class="sxs-lookup"><span data-stu-id="52e63-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52e63-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="52e63-111">Prerequisites</span></span>

<span data-ttu-id="52e63-112">Mielőtt hozzáadná a logót a webhely összes oldalához, végre kell hajtania ezeket a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="52e63-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="52e63-113">Töltse fel a logóját a digitáliseszköz-kezelőbe, amelyet az **Eszközök** oldalról érhet el.</span><span class="sxs-lookup"><span data-stu-id="52e63-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="52e63-114">Fejléctöredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="52e63-114">Create a header fragment.</span></span> <span data-ttu-id="52e63-115">A töredékek létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Töredékek használata](work-with-fragments.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="52e63-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="52e63-116">Adja meg a fejléctöredéket abban a sablonban, amelyet webhelyének oldalai használnak az elrendezéshez és a modulbeállításokhoz.</span><span class="sxs-lookup"><span data-stu-id="52e63-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="52e63-117">A sablonokkal kapcsolatos további információkért lásd: [Sablonok használata](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="52e63-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="52e63-118">Logó hozzáadása a fejléctöredékhez</span><span class="sxs-lookup"><span data-stu-id="52e63-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="52e63-119">A logó hozzáadásához a webhelye fejléctöredékéhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="52e63-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="52e63-120">A bal oldali navigációs panelen jelölje ki a **Töredékek** lehetőséget, majd válassza ki a létrehozott fejléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="52e63-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="52e63-121">Válassza a **Kivétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52e63-121">Select **Check out**.</span></span>
3. <span data-ttu-id="52e63-122">Bontsa ki a **Fejléc** helyet és a **Logó** helyet.</span><span class="sxs-lookup"><span data-stu-id="52e63-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="52e63-123">Válassza ki a **Logó** helyhez tartozó három pont gombot (**...**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="52e63-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="52e63-124">Válassza ki a logó modult.</span><span class="sxs-lookup"><span data-stu-id="52e63-124">Select the logo module.</span></span>
6. <span data-ttu-id="52e63-125">A jobb oldali tulajdonságok panelen konfigurálja a logó modult, hogy az Ön logóját jelenítse meg.</span><span class="sxs-lookup"><span data-stu-id="52e63-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="52e63-126">Mentse a fejléctöredéket, adja be és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="52e63-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="52e63-127">A frissített fejléctöredék közzététele után a webhely összes olyan oldala, amely a fejléctöredéket tartalmazó sablont használja, megjeleníti a logót.</span><span class="sxs-lookup"><span data-stu-id="52e63-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52e63-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="52e63-128">Additional resources</span></span>

[<span data-ttu-id="52e63-129">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="52e63-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="52e63-130">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="52e63-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="52e63-131">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="52e63-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="52e63-132">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="52e63-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="52e63-133">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="52e63-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="52e63-134">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="52e63-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="52e63-135">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="52e63-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

