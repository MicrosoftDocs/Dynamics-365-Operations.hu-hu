---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee2f74581ded6020d075377f931c465d7c89f9e5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211105"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="fb3a0-103">Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz</span><span class="sxs-lookup"><span data-stu-id="fb3a0-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fb3a0-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fb3a0-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="fb3a0-105">Overview</span></span>

<span data-ttu-id="fb3a0-106">Ha egy kérés nem sikerült, a kiszolgáló HTTP-állapotkódos hibajelzéseket ad ki.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="fb3a0-107">A 404-es állapotkódot rögzíti és adja vissza a program, ha nem találja meg a lapot, és az 500-as állapotkódot rögzíti és adja vissza a rendszer a kiszolgáló meghibásodása esetén.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="fb3a0-108">A Dynamics 365 Commerce alkalmazás felhasználói egyéni állapotkód hibaválaszoldalakat állíthatnak össze, amelyek ezeknél az állapotkód hibaüzenetek esetében megjelenítésre kerülnek a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="fb3a0-109">Állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="fb3a0-109">Build a status code error response page</span></span>

<span data-ttu-id="fb3a0-110">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="fb3a0-111">A kívánt webböngészőben jelentkezzen be a Dynamics 365 Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="fb3a0-112">Válassza ki a webhelyet, amelyhez a 4xx/5xx állapotkód hibaválaszoldalt össze kívánja állítani.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="fb3a0-113">Állítsa össze a sablont</span><span class="sxs-lookup"><span data-stu-id="fb3a0-113">Build the template</span></span>

<span data-ttu-id="fb3a0-114">Állapotkód hibaválaszoldal sablonjának összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="fb3a0-115">Ugorjon a **Sablonok** részre.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="fb3a0-116">Válassza az **Új** lehetőséget egy oldalsablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="fb3a0-117">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg az új sablon nevét, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="fb3a0-118">Állítsa össze a sablont a struktúra alapján, amelyet az állapotkód hibaválaszoldalának kíván adni.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="fb3a0-119">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="fb3a0-120">Az állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="fb3a0-120">Build the status code error response page</span></span>

<span data-ttu-id="fb3a0-121">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="fb3a0-122">Lépjen az **Oldalak** pontra.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="fb3a0-123">Válassza az **Új** lehetőséget egy oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="fb3a0-124">A **Sablon kiválasztása** párbeszédpanelen válasszon ki egy sablont, majd az **Oldal neve** területen írja be az állapotkód-válasz lap nevét.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="fb3a0-125">Hagyja üresen az **Oldal URL-címe** mezőt.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="fb3a0-126">Állítsa össze a lapot.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-126">Build the page.</span></span>
1. <span data-ttu-id="fb3a0-127">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="fb3a0-128">A 4xx és a 5xx állapotkódú hibákhoz külön állapotkód hibaválaszoldalakat lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="fb3a0-129">Másik lehetőségként ugyanaz az általános állapotkód hibaválaszoldal használható mindkét hibakategória esetén.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="fb3a0-130">Átirányítás beállítása az állapotkód hibaválaszoldal számára</span><span class="sxs-lookup"><span data-stu-id="fb3a0-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="fb3a0-131">Állapotkód hibaválaszoldal átirányításának beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="fb3a0-132">Lépjen az **URL-ek \> Új \> Új álnév** lehetőségre, majd válassza ki a korábban összeállított állapotkód hibaválaszoldalt.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="fb3a0-133">Az **Álnév** mezőbe írja be az **alapértelmezett-4xx** vagy az **alapértelmezett-5xx** értéket attól függően, hogy melyik állapotkód hibaválaszoldalhoz állít be átirányítást.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="fb3a0-134">Ezeket az álneveket közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-134">These aliases must be published.</span></span> <span data-ttu-id="fb3a0-135">Ellenkező esetben az átirányítás nem fog működni.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="fb3a0-136">A hivatkozás véglegesítéséhez válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="fb3a0-137">Ha egyetlen állapotkód-hibaválaszoldalt használ a mindkét hibakategória esetén, akkor ismételje meg ezt az eljárást, hogy egy álnevet hivatkozzon ugyanannak a lapnak a másik hibakategóriájához.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb3a0-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fb3a0-138">Additional resources</span></span>

[<span data-ttu-id="fb3a0-139">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="fb3a0-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="fb3a0-140">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fb3a0-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="fb3a0-141">Weblap URL-jének létrehozása</span><span class="sxs-lookup"><span data-stu-id="fb3a0-141">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]