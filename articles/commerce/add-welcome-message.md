---
title: Üdvözlő üzenet hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 25a4e91646916b03c8a138fc713577f429ab633c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697382"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="6b675-103">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6b675-103">Add a welcome message</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6b675-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.</span><span class="sxs-lookup"><span data-stu-id="6b675-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="6b675-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6b675-105">Overview</span></span>

<span data-ttu-id="6b675-106">Az e-kereskedelmi webhely üdvözlő üzenete tájékoztatja a látogatókat a folyamatban lévő akciókról, a webhely frissítéseiről, illetve az idényjellegű gyűjtemények elérhetőségéről.</span><span class="sxs-lookup"><span data-stu-id="6b675-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="6b675-107">Az üdvözlő üzenetet a figyelmeztetési modul segítségével lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="6b675-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="6b675-108">A figyelmeztetési modult hozzá kell adni a fejléctöredék **Hiba/Tájékoztató üzenetek** helyéhez.</span><span class="sxs-lookup"><span data-stu-id="6b675-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="6b675-109">A figyelmeztetési modul segítségével megadhatja a megjelenített szöveget, a szöveg színét és az igazítását.</span><span class="sxs-lookup"><span data-stu-id="6b675-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="6b675-110">Azt is megadhatja, hogy a webhely látogatói figyelmen kívül tudják-e hagyni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="6b675-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="6b675-111">Amikor egy üdvözlő üzenetet egy megosztott fejléctöredékhez adnak hozzá, ez minden olyan oldalon megjelenik, amely azt a sablont használja, amelyen a megosztott fejléctöredék szerepel.</span><span class="sxs-lookup"><span data-stu-id="6b675-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="6b675-112">Ha új üdvözlő üzenetet szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b675-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="6b675-113">A Dynamics 365 Commerce szolgáltatásban nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="6b675-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="6b675-114">Válassza ki a **Töredékek** pontot.</span><span class="sxs-lookup"><span data-stu-id="6b675-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="6b675-115">Válassza ki azt a fejléctöredéket, amelyhez hozzá szeretné adni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="6b675-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="6b675-116">Az oldalstruktúra-fában bontsa ki a **Hibaüzenetek/Tájékoztató üzenetek** elemet.</span><span class="sxs-lookup"><span data-stu-id="6b675-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="6b675-117">Válassza ki a figyelmeztetési modult.</span><span class="sxs-lookup"><span data-stu-id="6b675-117">Select the alert module.</span></span>

    <span data-ttu-id="6b675-118">Ha a figyelmeztető modul még nem létezik, akkor válassza a három pont gombot (**…**) a **Hibaüzenetek/Tájékoztató üzenetek** elemet, majd a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b675-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="6b675-119">Válassza ki a figyelmeztetési modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6b675-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="6b675-120">Válassza ki a jobb oldali ablaktáblában az **Adatok** lap **Adatforrás hozzáadása** elemét, majd a **Tartalom** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b675-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="6b675-121">A **Beviteli szöveg** mezőbe írja be az üdvözlő üzenet szövegét.</span><span class="sxs-lookup"><span data-stu-id="6b675-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="6b675-122">Mentse a fejléctöredéket, adja be és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="6b675-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="6b675-123">A kiválasztott fejléctöredéket használó összes webhelyoldal tetején megjelenik az üdvözlő üzenet.</span><span class="sxs-lookup"><span data-stu-id="6b675-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b675-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6b675-124">Additional resources</span></span>

[<span data-ttu-id="6b675-125">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6b675-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="6b675-126">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6b675-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="6b675-127">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6b675-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="6b675-128">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6b675-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="6b675-129">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="6b675-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="6b675-130">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="6b675-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

