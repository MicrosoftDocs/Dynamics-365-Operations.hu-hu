---
title: Láblécmodul
description: Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e81617979a945274500c9f4ceaa8078d8dfd79e8
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686718"
---
# <a name="footer-module"></a><span data-ttu-id="b6943-103">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="b6943-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="b6943-104">Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b6943-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b6943-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b6943-105">Overview</span></span>

<span data-ttu-id="b6943-106">A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b6943-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="b6943-107">Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.</span><span class="sxs-lookup"><span data-stu-id="b6943-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="b6943-108">A következő kép egy webhelyoldalon használt láblécmodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b6943-108">The following image shows an example of a footer module on a site page.</span></span>

![Példa egy lábléc modulra](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="b6943-110">Láblécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b6943-110">Footer module properties</span></span> 

<span data-ttu-id="b6943-111">A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="b6943-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="b6943-112">Emellett támogatja több lábléckategória modul hozzáadását is.</span><span class="sxs-lookup"><span data-stu-id="b6943-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="b6943-113">Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.</span><span class="sxs-lookup"><span data-stu-id="b6943-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="b6943-114">A láblécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="b6943-114">Modules available in a footer module</span></span>

<span data-ttu-id="b6943-115">**Láblécelemek** – Az láblécelemek modul tartalmaz egy fejlécet, egy képet és egy hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="b6943-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="b6943-116">A fejléc használható akár önmagában, akár egy képpel és hivatkozással együtt.</span><span class="sxs-lookup"><span data-stu-id="b6943-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="b6943-117">A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="b6943-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="b6943-118">**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz.</span><span class="sxs-lookup"><span data-stu-id="b6943-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="b6943-119">Kötelező megadni egy célt.</span><span class="sxs-lookup"><span data-stu-id="b6943-119">A destination is required.</span></span> <span data-ttu-id="b6943-120">Az alapértelmezett célérték a \#, amely a felhasználó a lap tetejére viszi.</span><span class="sxs-lookup"><span data-stu-id="b6943-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="b6943-121">Láblécmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="b6943-121">Create a footer module</span></span>

1. <span data-ttu-id="b6943-122">Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b6943-122">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="b6943-123">Az **Új oldaltöredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg az oldaltöredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b6943-123">In the **New page fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="b6943-124">Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6943-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b6943-125">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lábléckategória** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b6943-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b6943-126">A **Lábléckategória** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6943-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b6943-127">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Láblécelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b6943-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b6943-128">Válassza ki a **Láblécelem** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.</span><span class="sxs-lookup"><span data-stu-id="b6943-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="b6943-129">További láblécelemek hozzáadásához ismételje meg az 5–7. mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="b6943-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="b6943-130">Egy „vissza a tetejére” hivatkozás hozzáadásához a lábléchez, válassza ki a három pont gombot (**...**) a **Lábléckategória** hely esetében, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b6943-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="b6943-131">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Vissza a tetejére** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b6943-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b6943-132">Válassza ki a **Vissza a tetejére** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja szöveget és más modultulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="b6943-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="b6943-133">Válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b6943-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="b6943-134">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="b6943-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="b6943-135">Az **Alapértelmezett** lap **Lábléc** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="b6943-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="b6943-136">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b6943-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="b6943-137">Ha hozzáadja a laptöredéket a lapsablonokhoz, akkor segít biztosítani azt, hogy a lábléc minden oldalon megjeleníthető legyen.</span><span class="sxs-lookup"><span data-stu-id="b6943-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6943-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b6943-138">Additional resources</span></span>

[<span data-ttu-id="b6943-139">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="b6943-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b6943-140">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="b6943-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b6943-141">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="b6943-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b6943-142">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="b6943-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="b6943-143">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="b6943-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="b6943-144">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="b6943-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="b6943-145">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="b6943-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="b6943-146">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="b6943-146">Footer module</span></span>](author-footer-module.md)
