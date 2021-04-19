---
title: Promóciós szalagcím modul
description: Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: be3cc9729b58fce9ebc9885d8cb20b63114362a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796246"
---
# <a name="promo-banner-module"></a><span data-ttu-id="9f9ee-103">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="9f9ee-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f9ee-104">Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9f9ee-105">A promóciós szalagcím modulok a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="9f9ee-106">Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="9f9ee-107">A promóciós szalagcím modulok szöveges üzenetet és egy hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="9f9ee-108">Ha egy promóciós banner modulhoz több üzenetet ad, akkor egy olyan forgótár-szalagcím lesz, amely segítségével az ügyfelek végigpörgethetik az összes üzenetet.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="9f9ee-109">A promóciós szalagcím modulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="9f9ee-110">Az e-kereskedelmi promóciós szalagcím használatára példa</span><span class="sxs-lookup"><span data-stu-id="9f9ee-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="9f9ee-111">A webhely fejlécében a promóciós szalagcímeket a webhely egészére kiterjedő promóciók és üzenetek megjelenítésére lehet használni, ahogy az alábbi példákban is.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="9f9ee-112">„Az éves akció 10 napon belül lejár”</span><span class="sxs-lookup"><span data-stu-id="9f9ee-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="9f9ee-113">„Nagy megtakarítás az iskolakezdő akcióval.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-113">"Save big with back to school sale.</span></span> <span data-ttu-id="9f9ee-114">Vásároljon most.”</span><span class="sxs-lookup"><span data-stu-id="9f9ee-114">Shop Now."</span></span>

<span data-ttu-id="9f9ee-115">"Vásároljon Karácsonyra AKCIÓ!"</span><span class="sxs-lookup"><span data-stu-id="9f9ee-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="9f9ee-116">A következő kép egy promóciós bannert mutat be.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-116">The following image shows an example of a promo banner.</span></span>

![Példa egy promóciós banner modulra](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="9f9ee-118">Promóciós szalagcím modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="9f9ee-118">Promo banner module properties</span></span>

| <span data-ttu-id="9f9ee-119">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="9f9ee-119">Property name</span></span>             | <span data-ttu-id="9f9ee-120">Érték</span><span class="sxs-lookup"><span data-stu-id="9f9ee-120">Value</span></span>                              | <span data-ttu-id="9f9ee-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="9f9ee-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="9f9ee-122">Szalagüzenetek</span><span class="sxs-lookup"><span data-stu-id="9f9ee-122">Banner messages</span></span>           | <span data-ttu-id="9f9ee-123">Szöveg és hivatkozások</span><span class="sxs-lookup"><span data-stu-id="9f9ee-123">Text and links</span></span>                     | <span data-ttu-id="9f9ee-124">Szövegből és hivatkozásokból álló tömb.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-124">An array of text and links.</span></span> |
| <span data-ttu-id="9f9ee-125">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="9f9ee-125">Autoplay</span></span>                  | <span data-ttu-id="9f9ee-126">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="9f9ee-126">**True** or **False**</span></span>              | <span data-ttu-id="9f9ee-127">Olyan érték, amely jelzi, hogy az üzenetek automatikusan körbemennek-e, ha több üzenet van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="9f9ee-128">Diák áttűnési időköze</span><span class="sxs-lookup"><span data-stu-id="9f9ee-128">Slide transition interval</span></span> | <span data-ttu-id="9f9ee-129">Ezredmásodpercek száma (ms)</span><span class="sxs-lookup"><span data-stu-id="9f9ee-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="9f9ee-130">Az üzenetek átváltására használt időtartam.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="9f9ee-131">Elvetés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9f9ee-131">Allow dismiss</span></span>             | <span data-ttu-id="9f9ee-132">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="9f9ee-132">**True** or **False**</span></span>              | <span data-ttu-id="9f9ee-133">Ha az érték **Igaz**, akkor az ügyfelek elvetheti a figyelmeztetést.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="9f9ee-134">Forgótár-váltó megjelenítése</span><span class="sxs-lookup"><span data-stu-id="9f9ee-134">Show carousel flipper</span></span>     | <span data-ttu-id="9f9ee-135">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="9f9ee-135">**True** or **False**</span></span>              | <span data-ttu-id="9f9ee-136">Olyan érték, amely azt jelzi, hogy a körhintaváltók megjelenjenek-e, így a vevők több manuálisan váltogathatnak több szalagcímelem között.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="9f9ee-137">Szöveg igazítása</span><span class="sxs-lookup"><span data-stu-id="9f9ee-137">Text alignment</span></span>            | <span data-ttu-id="9f9ee-138">**Jobb**, **Bal** vagy **Közép**</span><span class="sxs-lookup"><span data-stu-id="9f9ee-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="9f9ee-139">A promóciós szalagcím modul szövegének igazítása.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="9f9ee-140">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="9f9ee-140">Link</span></span>                      | <span data-ttu-id="9f9ee-141">Egy URL-cím</span><span class="sxs-lookup"><span data-stu-id="9f9ee-141">A URL</span></span>                              | <span data-ttu-id="9f9ee-142">Az opcionális hivatkozás URL-címe.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="9f9ee-143">Promóciós szalagcím modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="9f9ee-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="9f9ee-144">A promóciós szalagcím modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="9f9ee-145">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="9f9ee-146">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **promóciós szalagcím sablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="9f9ee-147">Az **Oldalstruktúra** területen vegyen fel egy **Alapértelmezett oldal** modult a **Szövegtörzs** helyre.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="9f9ee-148">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="9f9ee-149">A most létrehozott sablon használatával hozzon létre egy **Promóciós szalagcím oldal** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="9f9ee-150">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="9f9ee-151">A jobb oldali ablaktáblában adja meg a **Tároló kitöltése** értékre a **Szélesség** beállítást.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="9f9ee-152">A **Oldalstruktúra** területen vegyen fel egy promóciós szalagcím modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="9f9ee-153">A szalagcím modul beállításainál vegyen fel egy vagy több szalagcímüzenetet.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="9f9ee-154">Minden üzenethez hivatkozással együtt szöveg tartozhat.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-154">Each message can have text together with a link.</span></span> <span data-ttu-id="9f9ee-155">A további tulajdonságokat módosíthatja, ha a modult további személyre szabására van szükség.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="9f9ee-156">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="9f9ee-157">A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="9f9ee-158">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="9f9ee-159">A promóciós szalagcím általában a lap fejlécének vagy egy alfejlécének helyén használatos.</span><span class="sxs-lookup"><span data-stu-id="9f9ee-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="9f9ee-160">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9f9ee-160">Additional resources</span></span>

[<span data-ttu-id="9f9ee-161">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="9f9ee-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9f9ee-162">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="9f9ee-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="9f9ee-163">Szövegterület-modul</span><span class="sxs-lookup"><span data-stu-id="9f9ee-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="9f9ee-164">Tartalomblokk-modul</span><span class="sxs-lookup"><span data-stu-id="9f9ee-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="9f9ee-165">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="9f9ee-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]