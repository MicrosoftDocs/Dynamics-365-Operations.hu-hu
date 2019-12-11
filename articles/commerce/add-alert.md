---
title: Figyelmeztetési modul
description: Ez a témakör a figyelmeztetésmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785352"
---
# <a name="alert-module"></a><span data-ttu-id="168d3-103">Figyelmeztetési modul</span><span class="sxs-lookup"><span data-stu-id="168d3-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="168d3-104">Ez a témakör a figyelmeztetésmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="168d3-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="168d3-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="168d3-105">Overview</span></span>

<span data-ttu-id="168d3-106">A figyelmeztetésmodul a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="168d3-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="168d3-107">A figyelmeztetésmodulok szöveges üzenetet és egy hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="168d3-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="168d3-108">Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="168d3-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="168d3-109">A figyelmeztetésmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="168d3-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="168d3-110">Példák az e-Commerce figyelmeztetésmoduljaira</span><span class="sxs-lookup"><span data-stu-id="168d3-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="168d3-111">A webhely fejlécében a figyelmeztetésmodulok a webhely egészére érvényes promóciók és üzenetek jelzésére használhatók.</span><span class="sxs-lookup"><span data-stu-id="168d3-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="168d3-112">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="168d3-112">Here are some examples:</span></span>

<span data-ttu-id="168d3-113">„Az éves akció 10 napon belül lejár”</span><span class="sxs-lookup"><span data-stu-id="168d3-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="168d3-114">„Nagy megtakarítás az iskolakezdő akcióval.</span><span class="sxs-lookup"><span data-stu-id="168d3-114">"Save big with back to school sale.</span></span> <span data-ttu-id="168d3-115">Vásároljon most.”</span><span class="sxs-lookup"><span data-stu-id="168d3-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="168d3-116">Figyelmeztetésmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="168d3-116">Alert module properties</span></span>

| <span data-ttu-id="168d3-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="168d3-117">Property name</span></span>  | <span data-ttu-id="168d3-118">Érték</span><span class="sxs-lookup"><span data-stu-id="168d3-118">Value</span></span>                              | <span data-ttu-id="168d3-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="168d3-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="168d3-120">Szöveg</span><span class="sxs-lookup"><span data-stu-id="168d3-120">Text</span></span>           | <span data-ttu-id="168d3-121">Szöveg</span><span class="sxs-lookup"><span data-stu-id="168d3-121">Text</span></span>                               | <span data-ttu-id="168d3-122">A figyelmeztetésmodulban megjelenő szöveges üzenet.</span><span class="sxs-lookup"><span data-stu-id="168d3-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="168d3-123">Szöveg igazítása</span><span class="sxs-lookup"><span data-stu-id="168d3-123">Text alignment</span></span> | <span data-ttu-id="168d3-124">**Jobb**, **Bal** vagy **Közép**</span><span class="sxs-lookup"><span data-stu-id="168d3-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="168d3-125">Az érték, amely meghatározza a szöveg igazítását a figyelmeztetésmodulban.</span><span class="sxs-lookup"><span data-stu-id="168d3-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="168d3-126">Figyelmeztetés elutasítása</span><span class="sxs-lookup"><span data-stu-id="168d3-126">Dismiss alert</span></span>  | <span data-ttu-id="168d3-127">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="168d3-127">**True** or **False**</span></span>              | <span data-ttu-id="168d3-128">Ha az érték **Igaz**, akkor a vevő elvetheti a figyelmeztetést.</span><span class="sxs-lookup"><span data-stu-id="168d3-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="168d3-129">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="168d3-129">Link</span></span>           | <span data-ttu-id="168d3-130">URL-cím</span><span class="sxs-lookup"><span data-stu-id="168d3-130">URL</span></span>                                | <span data-ttu-id="168d3-131">Az opcionális hivatkozás URL-címe.</span><span class="sxs-lookup"><span data-stu-id="168d3-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="168d3-132">Figyelmeztetésmodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="168d3-132">Add an alert module to a page</span></span> 

<span data-ttu-id="168d3-133">A figyelmeztetésmodulnak az oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="168d3-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="168d3-134">Hozzon létre egy **figyelmeztetéssablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="168d3-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="168d3-135">Az alapértelmezett lap **Fő** helyén adjon hozzá egy figyelmeztetésmodult.</span><span class="sxs-lookup"><span data-stu-id="168d3-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="168d3-136">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="168d3-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="168d3-137">A most létrehozott figyelmeztetéssablon használatával hozzon létre egy **figyelmeztetéslap** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="168d3-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="168d3-138">Az új lap **Fő** helyén adjon hozzá egy figyelmeztetésmodult.</span><span class="sxs-lookup"><span data-stu-id="168d3-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="168d3-139">A figyelmeztetésmodul beállításaiban adja meg a figyelmeztetés szövegét.</span><span class="sxs-lookup"><span data-stu-id="168d3-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="168d3-140">A további tulajdonságokat módosíthatja, ha a figyelmeztetésmodult tovább személyre szabására van szükség.</span><span class="sxs-lookup"><span data-stu-id="168d3-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="168d3-141">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="168d3-141">Save and preview the page.</span></span> <span data-ttu-id="168d3-142">A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="168d3-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="168d3-143">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="168d3-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="168d3-144">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="168d3-144">Additional resources</span></span>

[<span data-ttu-id="168d3-145">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="168d3-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="168d3-146">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="168d3-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="168d3-147">Tartalomgazdag blokkmodul</span><span class="sxs-lookup"><span data-stu-id="168d3-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="168d3-148">Tartalomelhelyezési modul</span><span class="sxs-lookup"><span data-stu-id="168d3-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="168d3-149">Funkciómodul</span><span class="sxs-lookup"><span data-stu-id="168d3-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="168d3-150">Főképmodul</span><span class="sxs-lookup"><span data-stu-id="168d3-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="168d3-151">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="168d3-151">Video player module</span></span>](add-video-player.md)
