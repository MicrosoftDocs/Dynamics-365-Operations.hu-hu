---
title: Promóciós szalagcím modul
description: Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: dae824cdbaaf56f85f125c5f36aaa56171bbd6bc
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411365"
---
# <a name="promo-banner-module"></a><span data-ttu-id="47389-103">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="47389-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47389-104">Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="47389-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="47389-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="47389-105">Overview</span></span>

<span data-ttu-id="47389-106">A promóciós szalagcím modulok a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="47389-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="47389-107">Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="47389-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="47389-108">A promóciós szalagcím modulok szöveges üzenetet és egy hivatkozást támogatnak.</span><span class="sxs-lookup"><span data-stu-id="47389-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="47389-109">Ha egy promóciós banner modulhoz több üzenetet ad, akkor egy olyan forgótár-szalagcím lesz, amely segítségével az ügyfelek végigpörgethetik az összes üzenetet.</span><span class="sxs-lookup"><span data-stu-id="47389-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="47389-110">A promóciós szalagcím modulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.</span><span class="sxs-lookup"><span data-stu-id="47389-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="47389-111">Az e-kereskedelmi promóciós szalagcím használatára példa</span><span class="sxs-lookup"><span data-stu-id="47389-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="47389-112">A webhely fejlécében a promóciós szalagcímeket a webhely egészére kiterjedő promóciók és üzenetek megjelenítésére lehet használni, ahogy az alábbi példákban is.</span><span class="sxs-lookup"><span data-stu-id="47389-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="47389-113">„Az éves akció 10 napon belül lejár”</span><span class="sxs-lookup"><span data-stu-id="47389-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="47389-114">„Nagy megtakarítás az iskolakezdő akcióval.</span><span class="sxs-lookup"><span data-stu-id="47389-114">"Save big with back to school sale.</span></span> <span data-ttu-id="47389-115">Vásároljon most.”</span><span class="sxs-lookup"><span data-stu-id="47389-115">Shop Now."</span></span>

<span data-ttu-id="47389-116">"Vásároljon Karácsonyra AKCIÓ!"</span><span class="sxs-lookup"><span data-stu-id="47389-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="47389-117">A következő kép egy promóciós bannert mutat be.</span><span class="sxs-lookup"><span data-stu-id="47389-117">The following image shows an example of a promo banner.</span></span>

![Példa egy promóciós banner modulra](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="47389-119">Promóciós szalagcím modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="47389-119">Promo banner module properties</span></span>

| <span data-ttu-id="47389-120">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="47389-120">Property name</span></span>             | <span data-ttu-id="47389-121">Érték</span><span class="sxs-lookup"><span data-stu-id="47389-121">Value</span></span>                              | <span data-ttu-id="47389-122">Leírás</span><span class="sxs-lookup"><span data-stu-id="47389-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="47389-123">Szalagüzenetek</span><span class="sxs-lookup"><span data-stu-id="47389-123">Banner messages</span></span>           | <span data-ttu-id="47389-124">Szöveg és hivatkozások</span><span class="sxs-lookup"><span data-stu-id="47389-124">Text and links</span></span>                     | <span data-ttu-id="47389-125">Szövegből és hivatkozásokból álló tömb.</span><span class="sxs-lookup"><span data-stu-id="47389-125">An array of text and links.</span></span> |
| <span data-ttu-id="47389-126">Automatikus lejátszás</span><span class="sxs-lookup"><span data-stu-id="47389-126">Autoplay</span></span>                  | <span data-ttu-id="47389-127">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="47389-127">**True** or **False**</span></span>              | <span data-ttu-id="47389-128">Olyan érték, amely jelzi, hogy az üzenetek automatikusan körbemennek-e, ha több üzenet van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="47389-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="47389-129">Diák áttűnési időköze</span><span class="sxs-lookup"><span data-stu-id="47389-129">Slide transition interval</span></span> | <span data-ttu-id="47389-130">Ezredmásodpercek száma (ms)</span><span class="sxs-lookup"><span data-stu-id="47389-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="47389-131">Az üzenetek átváltására használt időtartam.</span><span class="sxs-lookup"><span data-stu-id="47389-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="47389-132">Elvetés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="47389-132">Allow dismiss</span></span>             | <span data-ttu-id="47389-133">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="47389-133">**True** or **False**</span></span>              | <span data-ttu-id="47389-134">Ha az érték **Igaz**, akkor az ügyfelek elvetheti a figyelmeztetést.</span><span class="sxs-lookup"><span data-stu-id="47389-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="47389-135">Forgótár-váltó megjelenítése</span><span class="sxs-lookup"><span data-stu-id="47389-135">Show carousel flipper</span></span>     | <span data-ttu-id="47389-136">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="47389-136">**True** or **False**</span></span>              | <span data-ttu-id="47389-137">Olyan érték, amely azt jelzi, hogy a körhintaváltók megjelenjenek-e, így a vevők több manuálisan váltogathatnak több szalagcímelem között.</span><span class="sxs-lookup"><span data-stu-id="47389-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="47389-138">Szöveg igazítása</span><span class="sxs-lookup"><span data-stu-id="47389-138">Text alignment</span></span>            | <span data-ttu-id="47389-139">**Jobb**, **Bal** vagy **Közép**</span><span class="sxs-lookup"><span data-stu-id="47389-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="47389-140">A promóciós szalagcím modul szövegének igazítása.</span><span class="sxs-lookup"><span data-stu-id="47389-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="47389-141">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="47389-141">Link</span></span>                      | <span data-ttu-id="47389-142">Egy URL-cím</span><span class="sxs-lookup"><span data-stu-id="47389-142">A URL</span></span>                              | <span data-ttu-id="47389-143">Az opcionális hivatkozás URL-címe.</span><span class="sxs-lookup"><span data-stu-id="47389-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="47389-144">Promóciós szalagcím modul hozzáadása a laphoz</span><span class="sxs-lookup"><span data-stu-id="47389-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="47389-145">A promóciós szalagcím modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="47389-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="47389-146">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="47389-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="47389-147">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **promóciós szalagcím sablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="47389-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="47389-148">Az **Oldalstruktúra** területen vegyen fel egy **Alapértelmezett oldal** modult a **Szövegtörzs** helyre.</span><span class="sxs-lookup"><span data-stu-id="47389-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="47389-149">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="47389-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="47389-150">A most létrehozott sablon használatával hozzon létre egy **Promóciós szalagcím oldal** nevű lapot.</span><span class="sxs-lookup"><span data-stu-id="47389-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="47389-151">Az új lap **Fő** helyén adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="47389-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="47389-152">A jobb oldali ablaktáblában adja meg a **Tároló kitöltése** értékre a **Szélesség** beállítást.</span><span class="sxs-lookup"><span data-stu-id="47389-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="47389-153">A **Oldalstruktúra** területen vegyen fel egy promóciós szalagcím modult a tároló modulba.</span><span class="sxs-lookup"><span data-stu-id="47389-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="47389-154">A szalagcím modul beállításainál vegyen fel egy vagy több szalagcímüzenetet.</span><span class="sxs-lookup"><span data-stu-id="47389-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="47389-155">Minden üzenethez hivatkozással együtt szöveg tartozhat.</span><span class="sxs-lookup"><span data-stu-id="47389-155">Each message can have text together with a link.</span></span> <span data-ttu-id="47389-156">A további tulajdonságokat módosíthatja, ha a modult további személyre szabására van szükség.</span><span class="sxs-lookup"><span data-stu-id="47389-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="47389-157">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="47389-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="47389-158">A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="47389-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="47389-159">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="47389-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="47389-160">A promóciós szalagcím általában a lap fejlécének vagy egy alfejlécének helyén használatos.</span><span class="sxs-lookup"><span data-stu-id="47389-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="47389-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="47389-161">Additional resources</span></span>

[<span data-ttu-id="47389-162">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="47389-162">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="47389-163">Forgótármodul</span><span class="sxs-lookup"><span data-stu-id="47389-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="47389-164">Szövegblokk modul</span><span class="sxs-lookup"><span data-stu-id="47389-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="47389-165">Tartalomblokk modul</span><span class="sxs-lookup"><span data-stu-id="47389-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="47389-166">Videólejátszó modul</span><span class="sxs-lookup"><span data-stu-id="47389-166">Video player module</span></span>](add-video-player.md)
