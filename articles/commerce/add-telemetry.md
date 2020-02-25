---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001277"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="39dc8-103">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="39dc8-103">Add script code to site pages to support telemetry</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="39dc8-104">Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.</span><span class="sxs-lookup"><span data-stu-id="39dc8-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="39dc8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="39dc8-105">Overview</span></span>

<span data-ttu-id="39dc8-106">A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat.</span><span class="sxs-lookup"><span data-stu-id="39dc8-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="39dc8-107">Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="39dc8-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="39dc8-108">A legtöbb webanalitikai csomag megköveteli, hogy a webhely összes oldalán található HTML **\<head\>**-eleméhez hozzáadjon ügyféloldali parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="39dc8-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="39dc8-109">Az ebben a témakörben található utasítások a Microsoft Dynamics 365 Commerce által natív módon nem kínált egyéni ügyféloldali funkciókra is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="39dc8-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="39dc8-110">Újra felhasználható töredék létrehozása a parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="39dc8-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="39dc8-111">Miután létrehozott egy töredéket a parancsfájl kódjához, az újra felhasználható a webhelye összes lapján.</span><span class="sxs-lookup"><span data-stu-id="39dc8-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="39dc8-112">Lépjen a **Töredékek \> Új oldaltöredék** elemhez.</span><span class="sxs-lookup"><span data-stu-id="39dc8-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="39dc8-113">Válassza ki a **Külső parancsfájl** elemet, adja meg a töredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="39dc8-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="39dc8-114">A töredékhierarchiában válassza ki az **imént létrehozott töredék** alárendelt parancsfájl-betöltő modulját.</span><span class="sxs-lookup"><span data-stu-id="39dc8-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="39dc8-115">A jobb oldali tulajdonságpanelen adja meg az ügyféloldali parancsfájlt, és állítsa be szükség szerint a többi konfigurációs beállítást.</span><span class="sxs-lookup"><span data-stu-id="39dc8-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="39dc8-116">A töredék hozzáadása sablonokhoz</span><span class="sxs-lookup"><span data-stu-id="39dc8-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="39dc8-117">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="39dc8-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="39dc8-118">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="39dc8-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="39dc8-119">Válassza ki a **HTML-fejléc** helyhez tartozó három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="39dc8-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="39dc8-120">Válassza ki a parancsfájl kódjához létrehozott töredéket.</span><span class="sxs-lookup"><span data-stu-id="39dc8-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="39dc8-121">Mentse a sablont és adja be.</span><span class="sxs-lookup"><span data-stu-id="39dc8-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="39dc8-122">Miután befejezte a munkát, közzé kell tennie a töredéket és az alapsablont.</span><span class="sxs-lookup"><span data-stu-id="39dc8-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="39dc8-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="39dc8-123">Additional resources</span></span>

[<span data-ttu-id="39dc8-124">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="39dc8-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="39dc8-125">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="39dc8-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="39dc8-126">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="39dc8-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="39dc8-127">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="39dc8-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="39dc8-128">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="39dc8-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="39dc8-129">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="39dc8-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="39dc8-130">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="39dc8-130">Add languages to your site</span></span>](add-languages-to-site.md)

