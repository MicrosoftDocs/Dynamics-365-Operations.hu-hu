---
title: Közösségi megosztás modul
description: Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 0e7f30686894f9cf92257e99d95cc8b00f76f899
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234317"
---
# <a name="social-share-module"></a><span data-ttu-id="54772-103">Közösségi megosztási modul</span><span class="sxs-lookup"><span data-stu-id="54772-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="54772-104">Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="54772-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="54772-105">A Közösségi megosztás modulok lehetővé teszik a felhasználók számára, hogy megosszanak e-kereskedelmi oldal URL-címeket közösségi felületeken, mint a Facebook, a Twitter, a Pinterest és a LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="54772-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="54772-106">A webhely URL-címeit e-mailen keresztül is meg lehet osztani.</span><span class="sxs-lookup"><span data-stu-id="54772-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="54772-107">A Közösségi megosztási modulokat gyakran használják a termékek részletező oldalain (PDP-k), hogy segítsenek a felhasználóknak megosztani a termék adatait.</span><span class="sxs-lookup"><span data-stu-id="54772-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="54772-108">Minden közösségi megosztási modul egy tároló a közösségi megosztás elemmodulokhoz.</span><span class="sxs-lookup"><span data-stu-id="54772-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="54772-109">Minden közösségi megosztási modul beállítható úgy, hogy egy adott közösségi webhelyre mutasson.</span><span class="sxs-lookup"><span data-stu-id="54772-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="54772-110">Alaphelyzetben a Facebook, Twitter, Pinterest, LinkedIn és az e-mail támogatott.</span><span class="sxs-lookup"><span data-stu-id="54772-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="54772-111">Amikor a webhely felhasználója kiválasztja egy közösségi felület szimbólumát, egy HTML iframe-t indít el a megfelelő közösségi oldalra.</span><span class="sxs-lookup"><span data-stu-id="54772-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="54772-112">Az iFrame-en belül a felhasználó bejelentkezhet, és közzéteheti az éppen megtekintett tartalmat.</span><span class="sxs-lookup"><span data-stu-id="54772-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="54772-113">Minden közösségimédia-platform nyomon követhet a sütiket, így ez a modul megköveteli, hogy a webhely felhasználó elfogadja a cookie-beleegyezés értesítő üzenetet.</span><span class="sxs-lookup"><span data-stu-id="54772-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="54772-114">Ha nem fogadja el a cookie-hozzájárulást, akkor a modul el lesz rejtve a lapon.</span><span class="sxs-lookup"><span data-stu-id="54772-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="54772-115">További információ:- [Cookie-k megfelelősége](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="54772-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="54772-116">A következő ábra bemutatja a termék részletei oldalon használt közösségi megosztási modul egy példáját.</span><span class="sxs-lookup"><span data-stu-id="54772-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Példa egy közösségi megosztási modulra](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="54772-118">Közösségi megosztási modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="54772-118">Social share module properties</span></span>

| <span data-ttu-id="54772-119">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="54772-119">Property name</span></span>             | <span data-ttu-id="54772-120">Érték</span><span class="sxs-lookup"><span data-stu-id="54772-120">Value</span></span>                 | <span data-ttu-id="54772-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="54772-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="54772-122">Felirat</span><span class="sxs-lookup"><span data-stu-id="54772-122">Caption</span></span>                  | <span data-ttu-id="54772-123">Szöveg</span><span class="sxs-lookup"><span data-stu-id="54772-123">Text</span></span> | <span data-ttu-id="54772-124">Ez a tulajdonság adja meg a modul feliratát.</span><span class="sxs-lookup"><span data-stu-id="54772-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="54772-125">Tájolás</span><span class="sxs-lookup"><span data-stu-id="54772-125">Orientation</span></span> | <span data-ttu-id="54772-126">**Vízszintes** vagy **Függőleges**</span><span class="sxs-lookup"><span data-stu-id="54772-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="54772-127">Ez a tulajdonság határozza meg a közösségimédia-elemek tájolását.</span><span class="sxs-lookup"><span data-stu-id="54772-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="54772-128">Közösségi megosztási elem modultulajdonságai</span><span class="sxs-lookup"><span data-stu-id="54772-128">Social share item module properties</span></span>
| <span data-ttu-id="54772-129">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="54772-129">Property name</span></span>             | <span data-ttu-id="54772-130">Érték</span><span class="sxs-lookup"><span data-stu-id="54772-130">Value</span></span>                 | <span data-ttu-id="54772-131">Leírás</span><span class="sxs-lookup"><span data-stu-id="54772-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="54772-132">Közösségi média</span><span class="sxs-lookup"><span data-stu-id="54772-132">Social media</span></span>              | <span data-ttu-id="54772-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="54772-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="54772-134">Egy legördülő menü a közösségimédia-platformok listájával.</span><span class="sxs-lookup"><span data-stu-id="54772-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="54772-135">Ikon</span><span class="sxs-lookup"><span data-stu-id="54772-135">Icon</span></span> |<span data-ttu-id="54772-136">Kép</span><span class="sxs-lookup"><span data-stu-id="54772-136">Image</span></span>    | <span data-ttu-id="54772-137">Ez lesz a megfelelő közösségi médiához megjelenített kép.</span><span class="sxs-lookup"><span data-stu-id="54772-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="54772-138">Gyakorlati tanácsként a közösségi média-felület SDK-ját tekintse meg az egyes platformokhoz javasolt képekért.</span><span class="sxs-lookup"><span data-stu-id="54772-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="54772-139">Közösségimédia-modul hozzáadása egy vásárlásmező-modulhoz</span><span class="sxs-lookup"><span data-stu-id="54772-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="54772-140">Közösségimédia-modul hozzáadásához egy vásárlásmező-modulhoz kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="54772-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="54772-141">A Fabrikam webhelyén válassza ki az **Oldalak** lehetőséget, majd válassza ki a **DefaultPDP** a termékrészletek oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="54772-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="54772-142">A **Vásárlásmező (kötelező)** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="54772-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54772-143">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Közösségi megosztás** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="54772-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="54772-144">Az **Közösségi megosztás** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="54772-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54772-145">A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShare** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="54772-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="54772-146">A **SocialShare** modul tulajdonságok ablaktáblájában , a **Tájolás** területen válassza a **Vízszintes** elemet.</span><span class="sxs-lookup"><span data-stu-id="54772-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="54772-147">Szükség szerint adjon meg egy feliratot.</span><span class="sxs-lookup"><span data-stu-id="54772-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="54772-148">Az **SocialShare** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="54772-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="54772-149">A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShareItem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="54772-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="54772-150">A **SocialShareItem** modulban, a **Közösségi média** alatt válassza a **Facebook** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54772-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="54772-151">A **SocialShareItem** modulban az **Ikon** alatt válassza a **+ Kép hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54772-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="54772-152">A **Médiaválasztó** párbeszédpanelen válassza ki a Facebook logó képét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="54772-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="54772-153">Ha nincs Facebook logókép, válassza az **Új médiaelem feltöltése** lehetőséget, hogy feltöltsön egyet.</span><span class="sxs-lookup"><span data-stu-id="54772-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="54772-154">Szükség esetén konfiguráljon és adjon hozzá további **SocialShareItem** modulokat.</span><span class="sxs-lookup"><span data-stu-id="54772-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="54772-155">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="54772-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="54772-156">A lap a közösségi megosztás modult jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="54772-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="54772-157">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="54772-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54772-158">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="54772-158">Additional resources</span></span>

[<span data-ttu-id="54772-159">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="54772-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="54772-160">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="54772-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="54772-161">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="54772-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]