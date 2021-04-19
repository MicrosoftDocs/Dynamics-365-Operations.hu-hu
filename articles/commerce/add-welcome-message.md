---
title: Üdvözlő üzenet hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797383"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="89d0d-103">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89d0d-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89d0d-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni üdvözlő üzenetet a Microsoft Dynamics 365 Commerce-webhelyéhez.</span><span class="sxs-lookup"><span data-stu-id="89d0d-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="89d0d-105">Az e-kereskedelmi webhely üdvözlő üzenete tájékoztatja a látogatókat a folyamatban lévő akciókról, a webhely frissítéseiről, illetve az idényjellegű gyűjtemények elérhetőségéről.</span><span class="sxs-lookup"><span data-stu-id="89d0d-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="89d0d-106">Az üdvözlő üzenetet a figyelmeztetési modul segítségével lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="89d0d-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="89d0d-107">A figyelmeztetési modult hozzá kell adni a fejléctöredék **Hiba/Tájékoztató üzenetek** helyéhez.</span><span class="sxs-lookup"><span data-stu-id="89d0d-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="89d0d-108">A figyelmeztetési modul segítségével megadhatja a megjelenített szöveget, a szöveg színét és az igazítását.</span><span class="sxs-lookup"><span data-stu-id="89d0d-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="89d0d-109">Azt is megadhatja, hogy a webhely látogatói figyelmen kívül tudják-e hagyni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="89d0d-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="89d0d-110">Amikor egy üdvözlő üzenetet egy megosztott fejléctöredékhez adnak hozzá, ez minden olyan oldalon megjelenik, amely azt a sablont használja, amelyen a megosztott fejléctöredék szerepel.</span><span class="sxs-lookup"><span data-stu-id="89d0d-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="89d0d-111">Ha új üdvözlő üzenetet szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="89d0d-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="89d0d-112">Nyissa meg a webhelyét a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="89d0d-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="89d0d-113">Válassza ki a **Töredékek** pontot.</span><span class="sxs-lookup"><span data-stu-id="89d0d-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="89d0d-114">Válassza ki azt a fejléctöredéket, amelyhez hozzá szeretné adni az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="89d0d-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="89d0d-115">Az oldalstruktúra-fában bontsa ki a **Hibaüzenetek/Tájékoztató üzenetek** elemet.</span><span class="sxs-lookup"><span data-stu-id="89d0d-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="89d0d-116">Válassza ki a figyelmeztetési modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="89d0d-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="89d0d-117">Ha a figyelmeztető modul még nem létezik, akkor először válassza a három pont gombot (**…**) a **Hibaüzenetek/Tájékoztató üzenetek** elemet, majd a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89d0d-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="89d0d-118">Válassza ki a jobb oldali ablaktáblában az **Adatok** lap **Adatforrás hozzáadása** elemét, majd a **Tartalom** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89d0d-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="89d0d-119">A **Beviteli szöveg** mezőbe írja be az üdvözlő üzenet szövegét.</span><span class="sxs-lookup"><span data-stu-id="89d0d-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="89d0d-120">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a fejléctöredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="89d0d-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="89d0d-121">A kiválasztott fejléctöredéket használó összes webhelyoldal tetején megjelenik az üdvözlő üzenet.</span><span class="sxs-lookup"><span data-stu-id="89d0d-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89d0d-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="89d0d-122">Additional resources</span></span>

[<span data-ttu-id="89d0d-123">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89d0d-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="89d0d-124">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="89d0d-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="89d0d-125">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="89d0d-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="89d0d-126">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89d0d-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="89d0d-127">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89d0d-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="89d0d-128">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="89d0d-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="89d0d-129">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="89d0d-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
