---
title: Láblécmodul
description: Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697313"
---
# <a name="footer-module"></a><span data-ttu-id="1c7a8-103">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-103">Footer module</span></span>  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1c7a8-104">Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1c7a8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="1c7a8-105">Overview</span></span>

<span data-ttu-id="1c7a8-106">A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="1c7a8-107">Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="1c7a8-108">Láblécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="1c7a8-108">Footer module properties</span></span> 

<span data-ttu-id="1c7a8-109">A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-109">Like most containers, a footer module support properties for the heading and the width.</span></span> <span data-ttu-id="1c7a8-110">Emellett támogatja több lábléckategória modul hozzáadását is.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="1c7a8-111">Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="1c7a8-112">A láblécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="1c7a8-112">Modules available in a footer module</span></span>

<span data-ttu-id="1c7a8-113">**Láblécelemek** – Az láblécelemek modul tartalmaz egy fejlécet, egy képet és egy hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="1c7a8-114">A fejléc használható akár önmagában, akár egy képpel és hivatkozással együtt.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="1c7a8-115">A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="1c7a8-116">**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="1c7a8-117">Kötelező megadni egy célt.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-117">A destination is required.</span></span> <span data-ttu-id="1c7a8-118">Az alapértelmezett célérték a #, amely a felhasználó a lap tetejére viszi.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="1c7a8-119">Láblécmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="1c7a8-119">Author a footer module</span></span>

1. <span data-ttu-id="1c7a8-120">Válassza a navigációs ablak **Töredékek** elemét, majd válassza ki az **Új lap töredék** elemet.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="1c7a8-121">Az **Új lap töredék** párbeszédpanelen jelölje ki a láblécmodult, adja meg a laptöredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="1c7a8-122">A bal oldali fastruktúrában válassza ki a három pont gombot (**...**) a láblécmodul esetében, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1c7a8-123">A **Modul hozzáadása** párbeszédpanelen válassza ki a lábléckategória modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="1c7a8-124">A bal oldali fastruktúrában válassza ki a három pont gombot a lábléckategória modul esetében, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1c7a8-125">A **Modul hozzáadása** párbeszédpanelen válassza ki a láblécelem modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="1c7a8-126">A bal oldali fastruktúrában válassza ki a láblécelem modult.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="1c7a8-127">Ezután a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="1c7a8-128">További láblécelemek hozzáadásához ismételje meg az 5–7. lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="1c7a8-129">Egy „vissza a tetejére” hivatkozás hozzáadásához a lábléchez, válassza ki a három pont gombot a lábléckategória modul esetében, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="1c7a8-130">A **Modul hozzáadása** párbeszédpanelen válassza ki a vissza a tetejére modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="1c7a8-131">A bal oldali fastruktúrában válassza ki a vissza a tetejére modult.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="1c7a8-132">Ezután jobb oldali tulajdonságok panelen konfigurálja a vissza a tetejére modult az igényeinek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="1c7a8-133">Mentse az oldaltöredéket, adja be és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-133">Save the page fragment, check it in, and publish it.</span></span>

<span data-ttu-id="1c7a8-134">Hajtsa végre a következő lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="1c7a8-135">Az alapértelmezett lap **Fő** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="1c7a8-136">Mentse a sablont, adja be és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-136">Save the template, check it in, and publish it.</span></span>

<span data-ttu-id="1c7a8-137">Ha hozzáadja a laptöredéket a lapsablonokhoz, akkor segít biztosítani azt, hogy a lábléc minden oldalon megjeleníthető legyen.</span><span class="sxs-lookup"><span data-stu-id="1c7a8-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c7a8-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1c7a8-138">Additional resources</span></span>

[<span data-ttu-id="1c7a8-139">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="1c7a8-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1c7a8-140">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="1c7a8-141">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1c7a8-142">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1c7a8-143">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1c7a8-144">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="1c7a8-145">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="1c7a8-146">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="1c7a8-146">Footer module</span></span>](author-footer-module.md)
