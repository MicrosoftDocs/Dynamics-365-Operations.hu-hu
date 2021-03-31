---
title: Üdvözlő üzenet hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d17ad7cfd6f11e84fdd1c8ebccca6f786b83c62d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209155"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="6301d-103">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6301d-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6301d-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.</span><span class="sxs-lookup"><span data-stu-id="6301d-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="6301d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6301d-105">Overview</span></span>

<span data-ttu-id="6301d-106">Az e-kereskedelmi webhely üdvözlő üzenete tájékoztatja a látogatókat a folyamatban lévő akciókról, a webhely frissítéseiről, illetve az idényjellegű gyűjtemények elérhetőségéről.</span><span class="sxs-lookup"><span data-stu-id="6301d-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="6301d-107">Az üdvözlő üzenetet a figyelmeztetési modul segítségével lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="6301d-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="6301d-108">A figyelmeztetési modult hozzá kell adni a fejléctöredék **Hiba/Tájékoztató üzenetek** helyéhez.</span><span class="sxs-lookup"><span data-stu-id="6301d-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="6301d-109">A figyelmeztetési modul segítségével megadhatja a megjelenített szöveget, a szöveg színét és az igazítását.</span><span class="sxs-lookup"><span data-stu-id="6301d-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="6301d-110">Azt is megadhatja, hogy a webhely látogatói figyelmen kívül tudják-e hagyni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="6301d-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="6301d-111">Amikor egy üdvözlő üzenetet egy megosztott fejléctöredékhez adnak hozzá, ez minden olyan oldalon megjelenik, amely azt a sablont használja, amelyen a megosztott fejléctöredék szerepel.</span><span class="sxs-lookup"><span data-stu-id="6301d-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="6301d-112">Ha új üdvözlő üzenetet szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6301d-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="6301d-113">Nyissa meg a webhelyét a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="6301d-113">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="6301d-114">Válassza ki a **Töredékek** pontot.</span><span class="sxs-lookup"><span data-stu-id="6301d-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="6301d-115">Válassza ki azt a fejléctöredéket, amelyhez hozzá szeretné adni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="6301d-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="6301d-116">Az oldalstruktúra-fában bontsa ki a **Hibaüzenetek/Tájékoztató üzenetek** elemet.</span><span class="sxs-lookup"><span data-stu-id="6301d-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="6301d-117">Válassza ki a figyelmeztetési modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6301d-117">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="6301d-118">Ha a figyelmeztető modul még nem létezik, akkor először válassza a három pont gombot (**…**) a **Hibaüzenetek/Tájékoztató üzenetek** elemet, majd a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6301d-118">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="6301d-119">Válassza ki a jobb oldali ablaktáblában az **Adatok** lap **Adatforrás hozzáadása** elemét, majd a **Tartalom** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6301d-119">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="6301d-120">A **Beviteli szöveg** mezőbe írja be az üdvözlő üzenet szövegét.</span><span class="sxs-lookup"><span data-stu-id="6301d-120">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="6301d-121">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a fejléctöredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="6301d-121">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="6301d-122">A kiválasztott fejléctöredéket használó összes webhelyoldal tetején megjelenik az üdvözlő üzenet.</span><span class="sxs-lookup"><span data-stu-id="6301d-122">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6301d-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6301d-123">Additional resources</span></span>

[<span data-ttu-id="6301d-124">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6301d-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="6301d-125">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6301d-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="6301d-126">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="6301d-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="6301d-127">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6301d-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="6301d-128">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6301d-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="6301d-129">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="6301d-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="6301d-130">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="6301d-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]