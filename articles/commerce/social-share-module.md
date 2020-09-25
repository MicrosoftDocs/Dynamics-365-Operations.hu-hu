---
title: Közösségi megosztás modul
description: Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 0fd81aa1f4b1358528f0135c1334dc7b4ac4461f
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761395"
---
# <a name="social-share-module"></a><span data-ttu-id="dcd26-103">Közösségi megosztás modul</span><span class="sxs-lookup"><span data-stu-id="dcd26-103">Social share module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="dcd26-104">Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="dcd26-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dcd26-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="dcd26-105">Overview</span></span>

<span data-ttu-id="dcd26-106">A Közösségi megosztás modulok lehetővé teszik a felhasználók számára, hogy megosszanak e-kereskedelmi oldal URL-címeket közösségi felületeken, mint a Facebook, a Twitter, a Pinterest és a LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="dcd26-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="dcd26-107">A webhely URL-címeit e-mailen keresztül is meg lehet osztani.</span><span class="sxs-lookup"><span data-stu-id="dcd26-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="dcd26-108">A Közösségi megosztási modulokat gyakran használják a termékek részletező oldalain (PDP-k), hogy segítsenek a felhasználóknak megosztani a termék adatait.</span><span class="sxs-lookup"><span data-stu-id="dcd26-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="dcd26-109">Minden közösségi megosztási modul egy tároló a közösségi megosztás elemmodulokhoz.</span><span class="sxs-lookup"><span data-stu-id="dcd26-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="dcd26-110">Minden közösségi megosztási modul beállítható úgy, hogy egy adott közösségi webhelyre mutasson.</span><span class="sxs-lookup"><span data-stu-id="dcd26-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="dcd26-111">Alaphelyzetben a Facebook, Twitter, Pinterest, LinkedIn és az e-mail támogatott.</span><span class="sxs-lookup"><span data-stu-id="dcd26-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="dcd26-112">Amikor a webhely felhasználója kiválasztja egy közösségi felület szimbólumát, egy HTML iframe-t indít el a megfelelő közösségi oldalra.</span><span class="sxs-lookup"><span data-stu-id="dcd26-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="dcd26-113">Az iFrame-en belül a felhasználó bejelentkezhet, és közzéteheti az éppen megtekintett tartalmat.</span><span class="sxs-lookup"><span data-stu-id="dcd26-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="dcd26-114">Minden közösségimédia-platform nyomon követhet a sütiket, így ez a modul megköveteli, hogy a webhely felhasználó elfogadja a cookie-beleegyezés értesítő üzenetet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="dcd26-115">Ha nem fogadja el a cookie-hozzájárulást, akkor a modul el lesz rejtve a lapon.</span><span class="sxs-lookup"><span data-stu-id="dcd26-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="dcd26-116">További információ:- [Cookie-k megfelelősége](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="dcd26-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="dcd26-117">A következő ábra bemutatja a termék részletei oldalon használt közösségi megosztási modul egy példáját.</span><span class="sxs-lookup"><span data-stu-id="dcd26-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Példa egy közösségi megosztási modulra](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="dcd26-119">Közösségi megosztási modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="dcd26-119">Social share module properties</span></span>

| <span data-ttu-id="dcd26-120">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="dcd26-120">Property name</span></span>             | <span data-ttu-id="dcd26-121">Érték</span><span class="sxs-lookup"><span data-stu-id="dcd26-121">Value</span></span>                 | <span data-ttu-id="dcd26-122">Leírás</span><span class="sxs-lookup"><span data-stu-id="dcd26-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="dcd26-123">Felirat</span><span class="sxs-lookup"><span data-stu-id="dcd26-123">Caption</span></span>                  | <span data-ttu-id="dcd26-124">Szöveg</span><span class="sxs-lookup"><span data-stu-id="dcd26-124">Text</span></span> | <span data-ttu-id="dcd26-125">Ez a tulajdonság adja meg a modul feliratát.</span><span class="sxs-lookup"><span data-stu-id="dcd26-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="dcd26-126">Tájolás</span><span class="sxs-lookup"><span data-stu-id="dcd26-126">Orientation</span></span> | <span data-ttu-id="dcd26-127">**Vízszintes** vagy **Függőleges**</span><span class="sxs-lookup"><span data-stu-id="dcd26-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="dcd26-128">Ez a tulajdonság határozza meg a közösségimédia-elemek tájolását.</span><span class="sxs-lookup"><span data-stu-id="dcd26-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="dcd26-129">Közösségi megosztási elem modultulajdonságai</span><span class="sxs-lookup"><span data-stu-id="dcd26-129">Social share item module properties</span></span>
| <span data-ttu-id="dcd26-130">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="dcd26-130">Property name</span></span>             | <span data-ttu-id="dcd26-131">Érték</span><span class="sxs-lookup"><span data-stu-id="dcd26-131">Value</span></span>                 | <span data-ttu-id="dcd26-132">Leírás</span><span class="sxs-lookup"><span data-stu-id="dcd26-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="dcd26-133">Közösségi média</span><span class="sxs-lookup"><span data-stu-id="dcd26-133">Social media</span></span>              | <span data-ttu-id="dcd26-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="dcd26-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="dcd26-135">Egy legördülő menü a közösségimédia-platformok listájával.</span><span class="sxs-lookup"><span data-stu-id="dcd26-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="dcd26-136">Ikon</span><span class="sxs-lookup"><span data-stu-id="dcd26-136">Icon</span></span> |<span data-ttu-id="dcd26-137">Kép</span><span class="sxs-lookup"><span data-stu-id="dcd26-137">Image</span></span>    | <span data-ttu-id="dcd26-138">Ez lesz a megfelelő közösségi médiához megjelenített kép.</span><span class="sxs-lookup"><span data-stu-id="dcd26-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="dcd26-139">Gyakorlati tanácsként a közösségi média-felület SDK-ját tekintse meg az egyes platformokhoz javasolt képekért.</span><span class="sxs-lookup"><span data-stu-id="dcd26-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="dcd26-140">Közösségimédia-modul hozzáadása egy vásárlásmező-modulhoz</span><span class="sxs-lookup"><span data-stu-id="dcd26-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="dcd26-141">Közösségimédia-modul hozzáadásához egy vásárlásmező-modulhoz kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dcd26-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="dcd26-142">A Fabrikam webhelyén válassza ki az **Oldalak** lehetőséget, majd válassza ki a **DefaultPDP** a termékrészletek oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="dcd26-142">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="dcd26-143">A **Vásárlásmező (kötelező)** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-143">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dcd26-144">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Közösségi megosztás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dcd26-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="dcd26-145">Az **Közösségi megosztás** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-145">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dcd26-146">A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShare** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dcd26-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="dcd26-147">A **SocialShare** modul tulajdonságok ablaktáblájában , a **Tájolás** területen válassza a **Vízszintes** elemet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-147">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="dcd26-148">Szükség szerint adjon meg egy feliratot.</span><span class="sxs-lookup"><span data-stu-id="dcd26-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="dcd26-149">Az **SocialShare** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-149">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dcd26-150">A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShareItem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dcd26-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="dcd26-151">A **SocialShareItem** modulban, a **Közösségi média** alatt válassza a **Facebook** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dcd26-151">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="dcd26-152">A **SocialShareItem** modulban az **Ikon** alatt válassza a **+ Kép hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dcd26-152">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="dcd26-153">A **Médiaválasztó** párbeszédpanelen válassza ki a Facebook logó képét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dcd26-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="dcd26-154">Ha nincs Facebook logókép, válassza az **Új médiaelem feltöltése** lehetőséget, hogy feltöltsön egyet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="dcd26-155">Szükség esetén konfiguráljon és adjon hozzá további **SocialShareItem** modulokat.</span><span class="sxs-lookup"><span data-stu-id="dcd26-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="dcd26-156">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="dcd26-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="dcd26-157">A lap a közösségi megosztás modult jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dcd26-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="dcd26-158">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="dcd26-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dcd26-159">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dcd26-159">Additional resources</span></span>

[<span data-ttu-id="dcd26-160">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="dcd26-160">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dcd26-161">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="dcd26-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="dcd26-162">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="dcd26-162">Cookie compliance</span></span>](cookie-compliance.md)
