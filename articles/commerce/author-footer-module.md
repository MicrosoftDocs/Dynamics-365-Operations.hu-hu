---
title: Láblécmodul
description: Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d6e7b0ad4fe0723575a0ec55a9b02d110568db58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797233"
---
# <a name="footer-module"></a><span data-ttu-id="33c4d-103">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="33c4d-104">Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="33c4d-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="33c4d-105">A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="33c4d-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="33c4d-106">Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.</span><span class="sxs-lookup"><span data-stu-id="33c4d-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="33c4d-107">A következő kép egy webhelyoldalon használt láblécmodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="33c4d-107">The following image shows an example of a footer module on a site page.</span></span>

![Példa egy lábléc modulra](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="33c4d-109">Láblécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="33c4d-109">Footer module properties</span></span> 

<span data-ttu-id="33c4d-110">A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="33c4d-110">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="33c4d-111">Emellett támogatja több lábléckategória modul hozzáadását is.</span><span class="sxs-lookup"><span data-stu-id="33c4d-111">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="33c4d-112">Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.</span><span class="sxs-lookup"><span data-stu-id="33c4d-112">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="33c4d-113">A láblécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="33c4d-113">Modules available in a footer module</span></span>

<span data-ttu-id="33c4d-114">**Láblécelemek** – Az láblécelemek modul tartalmaz egy fejlécet, egy képet és egy hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="33c4d-114">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="33c4d-115">A fejléc használható akár önmagában, akár egy képpel és hivatkozással együtt.</span><span class="sxs-lookup"><span data-stu-id="33c4d-115">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="33c4d-116">A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="33c4d-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="33c4d-117">**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz.</span><span class="sxs-lookup"><span data-stu-id="33c4d-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="33c4d-118">Kötelező megadni egy célt.</span><span class="sxs-lookup"><span data-stu-id="33c4d-118">A destination is required.</span></span> <span data-ttu-id="33c4d-119">Az alapértelmezett célérték a \#, amely a felhasználó a lap tetejére viszi.</span><span class="sxs-lookup"><span data-stu-id="33c4d-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="33c4d-120">Láblécmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="33c4d-120">Create a footer module</span></span>

1. <span data-ttu-id="33c4d-121">Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="33c4d-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="33c4d-122">Az **Új töredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg a töredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="33c4d-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="33c4d-123">Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="33c4d-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="33c4d-124">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lábléckategória** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="33c4d-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="33c4d-125">A **Lábléckategória** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="33c4d-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="33c4d-126">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Láblécelem** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="33c4d-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="33c4d-127">Válassza ki a **Láblécelem** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.</span><span class="sxs-lookup"><span data-stu-id="33c4d-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="33c4d-128">További láblécelemek hozzáadásához ismételje meg az 5–7. mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="33c4d-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="33c4d-129">Egy „vissza a tetejére” hivatkozás hozzáadásához a lábléchez, válassza ki a három pont gombot (**...**) a **Lábléckategória** hely esetében, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="33c4d-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="33c4d-130">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Vissza a tetejére** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="33c4d-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="33c4d-131">Válassza ki a **Vissza a tetejére** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja szöveget és más modultulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="33c4d-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="33c4d-132">Válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="33c4d-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="33c4d-133">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="33c4d-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="33c4d-134">Az **Alapértelmezett** lap **Lábléc** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="33c4d-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="33c4d-135">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="33c4d-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="33c4d-136">Ha hozzáadja a töredéket a lapsablonokhoz, akkor segít biztosítani azt, hogy a lábléc minden oldalon megjeleníthető legyen.</span><span class="sxs-lookup"><span data-stu-id="33c4d-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33c4d-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="33c4d-137">Additional resources</span></span>

[<span data-ttu-id="33c4d-138">Modulkönyvtár – áttekintés</span><span class="sxs-lookup"><span data-stu-id="33c4d-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="33c4d-139">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="33c4d-140">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="33c4d-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="33c4d-141">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="33c4d-142">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="33c4d-143">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="33c4d-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="33c4d-144">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="33c4d-145">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="33c4d-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]