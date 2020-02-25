---
title: Promóciós szalagcím modul
description: Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025620"
---
# <a name="promo-banner-module"></a><span data-ttu-id="009b6-103">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="009b6-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="009b6-104">Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="009b6-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="009b6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="009b6-105">Overview</span></span>

<span data-ttu-id="009b6-106">A promóciós szalagcím modulok a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="009b6-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="009b6-107">Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="009b6-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="009b6-108">A promóciós szalagcím modulok szöveges üzenetet és egy hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="009b6-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="009b6-109">Ha egy promóciós banner modulhoz több üzenetet ad, akkor egy olyan forgótár-szalagcím lesz, amely segítségével az ügyfelek végigpörgethetik az összes üzenetet.</span><span class="sxs-lookup"><span data-stu-id="009b6-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="009b6-110">A promóciós szalagcím modulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="009b6-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="009b6-111">Az e-kereskedelmi promóciós szalagcím használatára példa</span><span class="sxs-lookup"><span data-stu-id="009b6-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="009b6-112">A webhely fejlécében a promóciós szalagcímeket a webhely egészére kiterjedő promóciók és üzenetek megjelenítésére lehet használni, ahogy az alábbi példákban is.</span><span class="sxs-lookup"><span data-stu-id="009b6-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="009b6-113">„Az éves akció 10 napon belül lejár”</span><span class="sxs-lookup"><span data-stu-id="009b6-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="009b6-114">„Nagy megtakarítás az iskolakezdő akcióval.</span><span class="sxs-lookup"><span data-stu-id="009b6-114">"Save big with back to school sale.</span></span> <span data-ttu-id="009b6-115">Vásároljon most.”</span><span class="sxs-lookup"><span data-stu-id="009b6-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="009b6-116">Promóciós szalagcím modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="009b6-116">Promo banner module properties</span></span>

| <span data-ttu-id="009b6-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="009b6-117">Property name</span></span>             | <span data-ttu-id="009b6-118">Value</span><span class="sxs-lookup"><span data-stu-id="009b6-118">Value</span></span>                              | <span data-ttu-id="009b6-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="009b6-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="009b6-120">Szalagüzenetek</span><span class="sxs-lookup"><span data-stu-id="009b6-120">Banner messages</span></span>           | <span data-ttu-id="009b6-121">Szöveg és hivatkozások</span><span class="sxs-lookup"><span data-stu-id="009b6-121">Text and links</span></span>                     | <span data-ttu-id="009b6-122">Szövegből és hivatkozásokból álló tömb.</span><span class="sxs-lookup"><span data-stu-id="009b6-122">An array of text and links.</span></span> |
| <span data-ttu-id="009b6-123">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="009b6-123">Autoplay</span></span>                  | <span data-ttu-id="009b6-124">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="009b6-124">**True** or **False**</span></span>              | <span data-ttu-id="009b6-125">Olyan érték, amely jelzi, hogy az üzenetek automatikusan körbemennek-e, ha több üzenet van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="009b6-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="009b6-126">Diák áttűnési időköze</span><span class="sxs-lookup"><span data-stu-id="009b6-126">Slide transition interval</span></span> | <span data-ttu-id="009b6-127">Ezredmásodpercek száma (ms)</span><span class="sxs-lookup"><span data-stu-id="009b6-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="009b6-128">Az üzenetek átváltására használt időtartam.</span><span class="sxs-lookup"><span data-stu-id="009b6-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="009b6-129">Elvetés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="009b6-129">Allow dismiss</span></span>             | <span data-ttu-id="009b6-130">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="009b6-130">**True** or **False**</span></span>              | <span data-ttu-id="009b6-131">Ha az érték **Igaz**, akkor az ügyfelek elvetheti a figyelmeztetést.</span><span class="sxs-lookup"><span data-stu-id="009b6-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="009b6-132">Forgótár-váltó megjelenítése</span><span class="sxs-lookup"><span data-stu-id="009b6-132">Show carousel flipper</span></span>     | <span data-ttu-id="009b6-133">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="009b6-133">**True** or **False**</span></span>              | <span data-ttu-id="009b6-134">Olyan érték, amely azt jelzi, hogy a körhintaváltók megjelenjenek-e, így a vevők több manuálisan váltogathatnak több szalagcímelem között.</span><span class="sxs-lookup"><span data-stu-id="009b6-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="009b6-135">Szöveg igazítása</span><span class="sxs-lookup"><span data-stu-id="009b6-135">Text alignment</span></span>            | <span data-ttu-id="009b6-136">**Jobb**, **Bal** vagy **Közép**</span><span class="sxs-lookup"><span data-stu-id="009b6-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="009b6-137">A promóciós szalagcím modul szövegének igazítása.</span><span class="sxs-lookup"><span data-stu-id="009b6-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="009b6-138">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="009b6-138">Link</span></span>                      | <span data-ttu-id="009b6-139">Egy URL-cím</span><span class="sxs-lookup"><span data-stu-id="009b6-139">A URL</span></span>                              | <span data-ttu-id="009b6-140">Az opcionális hivatkozás URL-címe.</span><span class="sxs-lookup"><span data-stu-id="009b6-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="009b6-141">Promóciós szalagcím modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="009b6-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="009b6-142">A promóciós szalagcím modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="009b6-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="009b6-143">Hozzon létre egy **promóciós szalagcím sablon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="009b6-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="009b6-144">Az **Oldalstruktúra** területen vegyen fel egy **Alapértelmezett oldal** modult a **Szövegtörzs** helyre.</span><span class="sxs-lookup"><span data-stu-id="009b6-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="009b6-145">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="009b6-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="009b6-146">A most létrehozott sablon használatával hozzon létre egy **Promóciós szalagcím oldal** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="009b6-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="009b6-147">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="009b6-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="009b6-148">A jobb oldali ablaktáblában adja meg a **Tároló kitöltése** értékre a **Szélesség** beállítást.</span><span class="sxs-lookup"><span data-stu-id="009b6-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="009b6-149">A **Oldalstruktúra** területen vegyen fel egy promóciós szalagcím modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="009b6-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="009b6-150">A szalagcím modul beállításainál vegyen fel egy vagy több szalagcímüzenetet.</span><span class="sxs-lookup"><span data-stu-id="009b6-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="009b6-151">Minden üzenethez hivatkozással együtt szöveg tartozhat.</span><span class="sxs-lookup"><span data-stu-id="009b6-151">Each message can have text together with a link.</span></span> <span data-ttu-id="009b6-152">A további tulajdonságokat módosíthatja, ha a modult további személyre szabására van szükség.</span><span class="sxs-lookup"><span data-stu-id="009b6-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="009b6-153">Mentse a lapot, és tekintse meg az előnézetét.</span><span class="sxs-lookup"><span data-stu-id="009b6-153">Save and preview the page.</span></span> <span data-ttu-id="009b6-154">A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="009b6-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="009b6-155">Fejezze be a lap szerkesztését, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="009b6-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="009b6-156">A promóciós szalagcím általában a lap fejlécének vagy egy alfejlécének helyén használatos.</span><span class="sxs-lookup"><span data-stu-id="009b6-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="009b6-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="009b6-157">Additional resources</span></span>

[<span data-ttu-id="009b6-158">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="009b6-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="009b6-159">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="009b6-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="009b6-160">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="009b6-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="009b6-161">Tartalomblokk modul</span><span class="sxs-lookup"><span data-stu-id="009b6-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="009b6-162">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="009b6-162">Video player module</span></span>](add-video-player.md)
