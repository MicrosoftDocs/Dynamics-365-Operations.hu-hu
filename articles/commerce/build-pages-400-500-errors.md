---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799647"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="02e18-103">Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz</span><span class="sxs-lookup"><span data-stu-id="02e18-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02e18-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.</span><span class="sxs-lookup"><span data-stu-id="02e18-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="02e18-105">Ha egy kérés nem sikerült, a kiszolgáló HTTP-állapotkódos hibajelzéseket ad ki.</span><span class="sxs-lookup"><span data-stu-id="02e18-105">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="02e18-106">A 404-es állapotkódot rögzíti és adja vissza a program, ha nem találja meg a lapot, és az 500-as állapotkódot rögzíti és adja vissza a rendszer a kiszolgáló meghibásodása esetén.</span><span class="sxs-lookup"><span data-stu-id="02e18-106">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="02e18-107">A Dynamics 365 Commerce alkalmazás felhasználói egyéni állapotkód hibaválaszoldalakat állíthatnak össze, amelyek ezeknél az állapotkód hibaüzenetek esetében megjelenítésre kerülnek a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="02e18-107">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="02e18-108">Állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="02e18-108">Build a status code error response page</span></span>

<span data-ttu-id="02e18-109">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="02e18-109">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="02e18-110">A kívánt webböngészőben jelentkezzen be a Dynamics 365 Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="02e18-110">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="02e18-111">Válassza ki a webhelyet, amelyhez a 4xx/5xx állapotkód hibaválaszoldalt össze kívánja állítani.</span><span class="sxs-lookup"><span data-stu-id="02e18-111">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="02e18-112">Állítsa össze a sablont</span><span class="sxs-lookup"><span data-stu-id="02e18-112">Build the template</span></span>

<span data-ttu-id="02e18-113">Állapotkód hibaválaszoldal sablonjának összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="02e18-113">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="02e18-114">Ugorjon a **Sablonok** részre.</span><span class="sxs-lookup"><span data-stu-id="02e18-114">Go to **Templates**.</span></span>
1. <span data-ttu-id="02e18-115">Válassza az **Új** lehetőséget egy oldalsablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="02e18-115">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="02e18-116">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg az új sablon nevét, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="02e18-116">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="02e18-117">Állítsa össze a sablont a struktúra alapján, amelyet az állapotkód hibaválaszoldalának kíván adni.</span><span class="sxs-lookup"><span data-stu-id="02e18-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="02e18-118">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="02e18-118">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="02e18-119">Az állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="02e18-119">Build the status code error response page</span></span>

<span data-ttu-id="02e18-120">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="02e18-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="02e18-121">Lépjen az **Oldalak** pontra.</span><span class="sxs-lookup"><span data-stu-id="02e18-121">Go to **Pages**.</span></span>
1. <span data-ttu-id="02e18-122">Válassza az **Új** lehetőséget egy oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="02e18-122">Select **New** to create a page.</span></span>
1. <span data-ttu-id="02e18-123">A **Sablon kiválasztása** párbeszédpanelen válasszon ki egy sablont, majd az **Oldal neve** területen írja be az állapotkód-válasz lap nevét.</span><span class="sxs-lookup"><span data-stu-id="02e18-123">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="02e18-124">Hagyja üresen az **Oldal URL-címe** mezőt.</span><span class="sxs-lookup"><span data-stu-id="02e18-124">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="02e18-125">Állítsa össze a lapot.</span><span class="sxs-lookup"><span data-stu-id="02e18-125">Build the page.</span></span>
1. <span data-ttu-id="02e18-126">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="02e18-126">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="02e18-127">A 4xx és a 5xx állapotkódú hibákhoz külön állapotkód hibaválaszoldalakat lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="02e18-127">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="02e18-128">Másik lehetőségként ugyanaz az általános állapotkód hibaválaszoldal használható mindkét hibakategória esetén.</span><span class="sxs-lookup"><span data-stu-id="02e18-128">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="02e18-129">Átirányítás beállítása az állapotkód hibaválaszoldal számára</span><span class="sxs-lookup"><span data-stu-id="02e18-129">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="02e18-130">Állapotkód hibaválaszoldal átirányításának beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="02e18-130">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="02e18-131">Lépjen az **URL-ek \> Új \> Új álnév** lehetőségre, majd válassza ki a korábban összeállított állapotkód hibaválaszoldalt.</span><span class="sxs-lookup"><span data-stu-id="02e18-131">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="02e18-132">Az **Álnév** mezőbe írja be az **alapértelmezett-4xx** vagy az **alapértelmezett-5xx** értéket attól függően, hogy melyik állapotkód hibaválaszoldalhoz állít be átirányítást.</span><span class="sxs-lookup"><span data-stu-id="02e18-132">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="02e18-133">Ezeket az álneveket közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="02e18-133">These aliases must be published.</span></span> <span data-ttu-id="02e18-134">Ellenkező esetben az átirányítás nem fog működni.</span><span class="sxs-lookup"><span data-stu-id="02e18-134">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="02e18-135">A hivatkozás véglegesítéséhez válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e18-135">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="02e18-136">Ha egyetlen állapotkód-hibaválaszoldalt használ a mindkét hibakategória esetén, akkor ismételje meg ezt az eljárást, hogy egy álnevet hivatkozzon ugyanannak a lapnak a másik hibakategóriájához.</span><span class="sxs-lookup"><span data-stu-id="02e18-136">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02e18-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="02e18-137">Additional resources</span></span>

[<span data-ttu-id="02e18-138">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="02e18-138">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="02e18-139">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="02e18-139">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="02e18-140">Weblap URL-jének létrehozása</span><span class="sxs-lookup"><span data-stu-id="02e18-140">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
