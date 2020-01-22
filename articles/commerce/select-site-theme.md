---
title: Webhely témájának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bcee3a3f29df316dff04cf22acbda7f968778c93
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914748"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="98770-103">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="98770-103">Select a site theme</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="98770-104">Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.</span><span class="sxs-lookup"><span data-stu-id="98770-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="98770-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="98770-105">Overview</span></span>

<span data-ttu-id="98770-106">A webhely elrendezését és stílusát (például a betűtípusokat, a méreteket és a színeket) a kiválasztott téma határozza meg, amely a webhelyre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="98770-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="98770-107">A témát a vállalat fejlesztője hozza létre és telepíti.</span><span class="sxs-lookup"><span data-stu-id="98770-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="98770-108">A témák áttekintését a [Témahasználat áttekintése](http://)című témakörben tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="98770-108">For an overview of themes, see [Theming overview](http://).</span></span> <span data-ttu-id="98770-109">További információ a témák létrehozásáról és telepítéséről: [Új téma létrehozása](http://).</span><span class="sxs-lookup"><span data-stu-id="98770-109">For more information about how to create and deploy themes, see [Create a new theme](http://).</span></span>

<span data-ttu-id="98770-110">Alapértelmezés szerint,m amikor először létrehoz egy webhelyet, az a **Gyár**elnevezésű témát használja.</span><span class="sxs-lookup"><span data-stu-id="98770-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="98770-111">Ez az alapértelmezett téma a kezdőkészlet részeként érhető el.</span><span class="sxs-lookup"><span data-stu-id="98770-111">This default theme is provided as part of the starter kit.</span></span> <span data-ttu-id="98770-112">Miután telepítette további témákat a webhelyhez, konfigurálhatja úgy a webhelyet, hogy valamelyiket használja ehelyett.</span><span class="sxs-lookup"><span data-stu-id="98770-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="98770-113">A webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="98770-113">Select the site theme</span></span>

<span data-ttu-id="98770-114">Ha ki szeretné választani a webhelyre alkalmazott témát, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="98770-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="98770-115">A webhelyszerkesztő környezetben menjen a weboldalához.</span><span class="sxs-lookup"><span data-stu-id="98770-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="98770-116">Lépjen a **Webhely kezelése** \> **Bővíthetőség** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98770-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="98770-117">A **Téma**területen válasszon ki egy témát a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="98770-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="98770-118">Ha a kiválasztott témát a webhelyre szeretné alkalmazni , válassza a **Mentés és közzététel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="98770-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="98770-119">A kiválasztott témát a program közzéteszi a webhelyen, mihelyt a **Mentés és közzététel** lehetőséget választja a **Bővíthetőség** oldalon.</span><span class="sxs-lookup"><span data-stu-id="98770-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="98770-120">Ha azt szeretné megtekintené egy téma előnézetét a webhelyen, anélkül, hogy alkalmazná azt akkor használhatja a fejlesztői vagy a védőfal-környezetet.</span><span class="sxs-lookup"><span data-stu-id="98770-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98770-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="98770-121">Additional resources</span></span>

[<span data-ttu-id="98770-122">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="98770-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="98770-123">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="98770-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="98770-124">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="98770-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="98770-125">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="98770-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="98770-126">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="98770-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="98770-127">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="98770-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="98770-128">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="98770-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
