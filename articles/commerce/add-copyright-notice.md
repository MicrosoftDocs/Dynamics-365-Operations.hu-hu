---
title: Szerzői jogi értesítés hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.
author: psimolin
manager: AnnBe
ms.date: 01/23/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 54b48ee74bc9d9f2b77f0584a0bf1739a8dfdbdb
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025482"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="c8405-103">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c8405-103">Add a copyright notice</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c8405-104">Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="c8405-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8405-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c8405-105">Prerequisites</span></span>

<span data-ttu-id="c8405-106">Ahhoz, hogy szerzői jogi nyilatkozatot adhasson a webhelyhez, a következő elemeket kell megadnia:</span><span class="sxs-lookup"><span data-stu-id="c8405-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="c8405-107">Közös lábléctöredéket tartalmazó sablon.</span><span class="sxs-lookup"><span data-stu-id="c8405-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="c8405-108">Az adott sablont használó oldal.</span><span class="sxs-lookup"><span data-stu-id="c8405-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="c8405-109">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c8405-109">Add a copyright notice</span></span>

<span data-ttu-id="c8405-110">A következő lépésekkel lehet hozzáadni egy szerzői jogi nyilatkozatot az összes olyan oldal aljához, amely egy adott sablont használ.</span><span class="sxs-lookup"><span data-stu-id="c8405-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="c8405-111">Lépjen a **Töredékek** pontra, majd válassza az **Új oldaltöredék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8405-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="c8405-112">A párbeszédpanelen válassza ki a **lábléc** modult, majd nevezze el a töredéket.</span><span class="sxs-lookup"><span data-stu-id="c8405-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="c8405-113">Írja be például a **Lábléc-Szerzői jog** értéket.</span><span class="sxs-lookup"><span data-stu-id="c8405-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="c8405-114">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8405-114">Select **OK**.</span></span>
1. <span data-ttu-id="c8405-115">A navigációs panelen válassza ki az válassza ki a **Lábléc** melletti három pontot (**…**) majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c8405-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="c8405-116">A párbeszédpanelen válassza ki a **Lábléc-kategória** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8405-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="c8405-117">A navigációs panelen válassza ki az válassza ki a **Lábléc-kategória** melletti három pontot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c8405-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="c8405-118">A párbeszédpanelen válassza ki a **Szövegblokk** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8405-118">In the dialog box, select **Text block**, and then select **OK**.</span></span>
1. <span data-ttu-id="c8405-119">A navigációs ablakban válassza ki a **Szövegblokk** elemet.</span><span class="sxs-lookup"><span data-stu-id="c8405-119">In the navigation pane, select **Text block**.</span></span>
1. <span data-ttu-id="c8405-120">A jobb oldali Tulajdonságok ablaktáblában, a **Bekezdés** mezőbe vegye fel a szerzői joggal kapcsolatos üzenetet.</span><span class="sxs-lookup"><span data-stu-id="c8405-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="c8405-121">Írja be például a következőt: **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="c8405-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="c8405-122">Válassza a **Mentés** parancsot, majd a **Beadás** elemet végül a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8405-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="c8405-123">Nyissa meg a **Sablonok** elemet, válasszon ki egy sablont, majd válassza a **Kivétel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c8405-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="c8405-124">Az **Oldalstruktúra** alatt bontsa ki a **Szövegtörzs** elemet, majd az **Alapértelmezett oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c8405-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="c8405-125">Válassza ki a **Lábléchely** hely melletti három pont gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c8405-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="c8405-126">Válassza ki a korábban létrehozott töredéket, majd válassza a **Kiválasztás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c8405-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="c8405-127">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="c8405-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="c8405-128">A szerzői jogi nyilatkozatot tartalmazó lábléc automatikusan megjelenik a kijelölt sablont használó oldalak alján.</span><span class="sxs-lookup"><span data-stu-id="c8405-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8405-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c8405-129">Additional resources</span></span>

[<span data-ttu-id="c8405-130">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c8405-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="c8405-131">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="c8405-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="c8405-132">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="c8405-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="c8405-133">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c8405-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="c8405-134">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c8405-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="c8405-135">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="c8405-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="c8405-136">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="c8405-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

