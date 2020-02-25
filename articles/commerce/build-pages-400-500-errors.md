---
title: Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001128"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="85684-103">Egyéni válaszlapok összeállítása a 4xx/5xx állapotkódhibákhoz</span><span class="sxs-lookup"><span data-stu-id="85684-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="85684-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce szerkesztési eszközeivel egyéni válaszoldalakat létrehozni a 4xx és 5xx állapotkódú hibákhoz.</span><span class="sxs-lookup"><span data-stu-id="85684-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="85684-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="85684-105">Overview</span></span>

<span data-ttu-id="85684-106">Ha egy kérés nem sikerült, a kiszolgáló HTTP-állapotkódos hibajelzéseket ad ki.</span><span class="sxs-lookup"><span data-stu-id="85684-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="85684-107">A 404-es állapotkódot rögzíti és adja vissza a program, ha nem találja meg a lapot, és az 500-as állapotkódot rögzíti és adja vissza a rendszer a kiszolgáló meghibásodása esetén.</span><span class="sxs-lookup"><span data-stu-id="85684-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="85684-108">A Dynamics 365 Commerce alkalmazás felhasználói egyéni állapotkód hibaválaszoldalakat állíthatnak össze, amelyek ezeknél az állapotkód hibaüzenetek esetében megjelenítésre kerülnek a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="85684-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="85684-109">Állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="85684-109">Build a status code error response page</span></span>

<span data-ttu-id="85684-110">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85684-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="85684-111">A kívánt webböngészőben jelentkezzen be a Dynamics 365 Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="85684-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="85684-112">Válassza ki a webhelyet, amelyhez a 4xx/5xx állapotkód hibaválaszoldalt össze kívánja állítani.</span><span class="sxs-lookup"><span data-stu-id="85684-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="85684-113">Állítsa össze a sablont</span><span class="sxs-lookup"><span data-stu-id="85684-113">Build the template</span></span>

<span data-ttu-id="85684-114">Állapotkód hibaválaszoldal sablonjának összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85684-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="85684-115">Lépjen a **Sablonok \> Új sablon** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="85684-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="85684-116">Nevezze el az új sablont.</span><span class="sxs-lookup"><span data-stu-id="85684-116">Name the new template.</span></span>
1. <span data-ttu-id="85684-117">Állítsa össze a sablont a struktúra alapján, amelyet az állapotkód hibaválaszoldalának kíván adni.</span><span class="sxs-lookup"><span data-stu-id="85684-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="85684-118">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="85684-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="85684-119">Az állapotkód hibaválaszoldal összeállítása</span><span class="sxs-lookup"><span data-stu-id="85684-119">Build the status code error response page</span></span>

<span data-ttu-id="85684-120">Állapotkód hibaválaszoldal összeállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85684-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="85684-121">Lépjen a **Lapok \> Új lap** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="85684-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="85684-122">Nevezze el az állapotkód hibaválaszoldalt, de **ne** állítsa be az **URL** mezőt.</span><span class="sxs-lookup"><span data-stu-id="85684-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="85684-123">Állítsa össze a lapot.</span><span class="sxs-lookup"><span data-stu-id="85684-123">Build the page.</span></span>
1. <span data-ttu-id="85684-124">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="85684-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="85684-125">A 4xx és a 5xx állapotkódú hibákhoz külön állapotkód hibaválaszoldalakat lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="85684-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="85684-126">Másik lehetőségként ugyanaz az általános állapotkód hibaválaszoldal használható mindkét hibakategória esetén.</span><span class="sxs-lookup"><span data-stu-id="85684-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="85684-127">Átirányítás beállítása az állapotkód hibaválaszoldal számára</span><span class="sxs-lookup"><span data-stu-id="85684-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="85684-128">Állapotkód hibaválaszoldal átirányításának beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85684-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="85684-129">Lépjen az **URL-ek \> Új \> Új álnév** lehetőségre, majd válassza ki a korábban összeállított állapotkód hibaválaszoldalt.</span><span class="sxs-lookup"><span data-stu-id="85684-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="85684-130">Az **Álnév** mezőbe írja be az **alapértelmezett-4xx** vagy az **alapértelmezett-5xx** értéket attól függően, hogy melyik állapotkód hibaválaszoldalhoz állít be átirányítást.</span><span class="sxs-lookup"><span data-stu-id="85684-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="85684-131">Ezeket az álneveket közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="85684-131">These aliases must be published.</span></span> <span data-ttu-id="85684-132">Ellenkező esetben az átirányítás nem fog működni.</span><span class="sxs-lookup"><span data-stu-id="85684-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="85684-133">A hivatkozás véglegesítéséhez válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="85684-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="85684-134">Ha egyetlen állapotkód-hibaválaszoldalt használ a mindkét hibakategória esetén, akkor ismételje meg ezt az eljárást, hogy egy álnevet hivatkozzon ugyanannak a lapnak a másik hibakategóriájához.</span><span class="sxs-lookup"><span data-stu-id="85684-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85684-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="85684-135">Additional resources</span></span>

[<span data-ttu-id="85684-136">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="85684-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="85684-137">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="85684-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="85684-138">Weblap URL-jének létrehozása</span><span class="sxs-lookup"><span data-stu-id="85684-138">Create a page URL</span></span>](create-page-url.md)
