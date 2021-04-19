---
title: Webhely témájának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e11e2ffafa29dfe4ad7a4a8e4d14e9d7c74c31f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794067"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="1eb7d-103">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1eb7d-104">Ez a témakör azt mutatja be, hogyan lehet egy webhely témáját beállítani vagy módosítani a Microsoft Dynamics 365 Commerce megoldásban.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1eb7d-105">A webhely elrendezését és stílusát (például a betűtípusokat, a méreteket és a színeket) a kiválasztott téma határozza meg, amely a webhelyre alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-105">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="1eb7d-106">A témát a vállalat fejlesztője hozza létre és telepíti.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-106">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="1eb7d-107">A témák áttekintését a [Témahasználat áttekintése](e-commerce-extensibility/theming.md)című témakörben tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-107">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="1eb7d-108">További információ a témák létrehozásáról és telepítéséről: [Új téma létrehozása](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="1eb7d-108">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="1eb7d-109">Alapértelmezés szerint,m amikor először létrehoz egy webhelyet, az a **Gyár** elnevezésű témát használja.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-109">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="1eb7d-110">Ez az alapértelmezett téma a Commerce modulkönyvtár részeként érhető el.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-110">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="1eb7d-111">Miután telepítette további témákat a webhelyhez, konfigurálhatja úgy a webhelyet, hogy valamelyiket használja ehelyett.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-111">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="1eb7d-112">A webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-112">Select the site theme</span></span>

<span data-ttu-id="1eb7d-113">Ha ki szeretné választani a webhelyre alkalmazott témát, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-113">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="1eb7d-114">A webhelyszerkesztő környezetben menjen a weboldalához.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-114">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="1eb7d-115">Lépjen a **Webhely kezelése** \> **Bővíthetőség** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-115">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="1eb7d-116">A **Téma** területen válasszon ki egy témát a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-116">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="1eb7d-117">Ha a kiválasztott témát a webhelyre szeretné alkalmazni , válassza a **Mentés és közzététel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-117">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb7d-118">A kiválasztott témát a program közzéteszi a webhelyen, mihelyt a **Mentés és közzététel** lehetőséget választja a **Bővíthetőség** oldalon.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-118">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="1eb7d-119">Ha azt szeretné megtekintené egy téma előnézetét a webhelyen, anélkül, hogy alkalmazná azt akkor használhatja a fejlesztői vagy a védőfal-környezetet.</span><span class="sxs-lookup"><span data-stu-id="1eb7d-119">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1eb7d-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1eb7d-120">Additional resources</span></span>

[<span data-ttu-id="1eb7d-121">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-121">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="1eb7d-122">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="1eb7d-122">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="1eb7d-123">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-123">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="1eb7d-124">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-124">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="1eb7d-125">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-125">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="1eb7d-126">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="1eb7d-126">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="1eb7d-127">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="1eb7d-127">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="1eb7d-128">Témahasználat áttekintése</span><span class="sxs-lookup"><span data-stu-id="1eb7d-128">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="1eb7d-129">Új téma létrehozása</span><span class="sxs-lookup"><span data-stu-id="1eb7d-129">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
