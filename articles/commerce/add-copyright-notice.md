---
title: Szerzői jogi értesítés hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.
author: psimolin
manager: AnnBe
ms.date: 10/31/2019
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
ms.openlocfilehash: 39135a2eca25336097ee9eddf06dc6709c102571
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696945"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="57bd7-103">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="57bd7-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="57bd7-104">Ez a témakör azt mutatja be, hogyan lehet az e-kereskedelmi webhelyhez szerzői jogi nyilatkozatot hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="57bd7-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57bd7-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="57bd7-105">Prerequisites</span></span>

<span data-ttu-id="57bd7-106">Ahhoz, hogy szerzői jogi nyilatkozatot adhasson a webhelyhez, a következő elemeket kell megadnia:</span><span class="sxs-lookup"><span data-stu-id="57bd7-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="57bd7-107">Közös lábléctöredéket tartalmazó sablon.</span><span class="sxs-lookup"><span data-stu-id="57bd7-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="57bd7-108">Az adott sablont használó oldal.</span><span class="sxs-lookup"><span data-stu-id="57bd7-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="57bd7-109">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="57bd7-109">Add a copyright notice</span></span>

<span data-ttu-id="57bd7-110">A következő lépésekkel lehet hozzáadni egy szerzői jogi nyilatkozatot az összes olyan oldal aljához, amely egy adott sablont használ.</span><span class="sxs-lookup"><span data-stu-id="57bd7-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="57bd7-111">Lépjen a **Töredékek** pontra, majd válassza az **Új oldaltöredék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57bd7-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="57bd7-112">A párbeszédpanelen válassza ki a **lábléc** modult, majd nevezze el a töredéket.</span><span class="sxs-lookup"><span data-stu-id="57bd7-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="57bd7-113">Írja be például a **Lábléc-Szerzői jog** értéket.</span><span class="sxs-lookup"><span data-stu-id="57bd7-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="57bd7-114">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57bd7-114">Select **OK**.</span></span>
1. <span data-ttu-id="57bd7-115">A navigációs panelen válassza ki az válassza ki a **Lábléc** melletti három pontot (**…**) majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="57bd7-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="57bd7-116">A párbeszédpanelen válassza ki a **Lábléc-kategória** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57bd7-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="57bd7-117">A navigációs panelen válassza ki az válassza ki a **Lábléc-kategória** melletti három pontot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="57bd7-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="57bd7-118">A párbeszédablakban válassza ki a **Tartalomgazdag blokk elem** lehetőséget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57bd7-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="57bd7-119">A navigációs ablakban válassza ki a **Tartalomgazdag blokkelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57bd7-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="57bd7-120">A jobb oldali Tulajdonságok ablaktáblában, a **Bekezdés** mezőbe vegye fel a szerzői joggal kapcsolatos üzenetet.</span><span class="sxs-lookup"><span data-stu-id="57bd7-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="57bd7-121">Írja be például a következőt: **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="57bd7-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="57bd7-122">Válassza a **Mentés** parancsot, majd a **Beadás** elemet végül a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57bd7-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="57bd7-123">Nyissa meg a **Sablonok** elemet, válasszon ki egy sablont, majd válassza a **Kivétel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="57bd7-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="57bd7-124">Az **Oldalstruktúra** alatt bontsa ki a **Szövegtörzs** elemet, majd az **Alapértelmezett oldal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57bd7-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="57bd7-125">Válassza ki a **Lábléchely** hely melletti három pont gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="57bd7-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="57bd7-126">Válassza ki a korábban létrehozott töredéket, majd válassza a **Kiválasztás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="57bd7-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="57bd7-127">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="57bd7-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="57bd7-128">A szerzői jogi nyilatkozatot tartalmazó lábléc automatikusan megjelenik a kijelölt sablont használó oldalak alján.</span><span class="sxs-lookup"><span data-stu-id="57bd7-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57bd7-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="57bd7-129">Additional resources</span></span>

[<span data-ttu-id="57bd7-130">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="57bd7-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="57bd7-131">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="57bd7-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="57bd7-132">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="57bd7-132">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="57bd7-133">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="57bd7-133">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="57bd7-134">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="57bd7-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="57bd7-135">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="57bd7-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

