---
title: Webhely-navigáció testreszabása
description: Ez a témakör azt mutatja be, hogyan lehet testreszabott online navigációs hierarchiát létrehozni a böngészésre szánt termékek rendszerezéséhez a Microsoft Dynamics 365 Commerce webhelyén.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2235510c7ef386d66fe3b137f8e791d14706379
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001829"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="c52df-103">Webhely-navigáció testreszabása</span><span class="sxs-lookup"><span data-stu-id="c52df-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c52df-104">Ez a témakör azt mutatja be, hogyan lehet testreszabott online navigációs hierarchiát létrehozni a böngészésre szánt termékek rendszerezéséhez a Microsoft Dynamics 365 Commerce webhelyén.</span><span class="sxs-lookup"><span data-stu-id="c52df-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="c52df-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c52df-105">Overview</span></span>

<span data-ttu-id="c52df-106">Az online kirakatok általában lehetővé teszik a vevők számára, hogy a termékkategóriák között navigálva felfedezzék és böngésszék a termékeket.</span><span class="sxs-lookup"><span data-stu-id="c52df-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="c52df-107">Ezt a lehetőséget általában a lapok felső részén található fülek, illetve a bal oldali navigációs sáv biztosítja.</span><span class="sxs-lookup"><span data-stu-id="c52df-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="c52df-108">A Dynamics 365 Commerce alkalmazásban létrehozhatja és kezelheti a kategórianavigáció hierarchikus szerkezetét, valamint a különböző kategóriákba tartozó termékeket.</span><span class="sxs-lookup"><span data-stu-id="c52df-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="c52df-109">Csatorna navigációs hierarchiájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="c52df-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="c52df-110">Csatorna navigációs hierarchiájának létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c52df-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="c52df-111">Ugorjon a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kategóriák és termékmenedzsment** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c52df-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="c52df-112">Válassza ki a **Kategóriahierarchiák**, majd az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="c52df-113">Nevezze le a hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="c52df-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c52df-114">A legfelső kategória, amelyet létrehoz, a gyökér kategória csomópontja.</span><span class="sxs-lookup"><span data-stu-id="c52df-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="c52df-115">A webhelyen nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="c52df-115">It won't be shown on your site.</span></span> <span data-ttu-id="c52df-116">Ha olyan kategóriahierarchiát szeretne létrehozni, ahol egyetlen felső szintű csomópont jelenik meg a webhelyen, hozza létre és nevezze el a kategóriát a gyökér kategóriájának gyermekeként.</span><span class="sxs-lookup"><span data-stu-id="c52df-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="c52df-117">Válassza ki az **Új kategória-csomópont** lehetőséget, és nevezze el a kategóriát.</span><span class="sxs-lookup"><span data-stu-id="c52df-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="c52df-118">Szükség szerint folytassa testvér- és gyermekkategóriák létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="c52df-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="c52df-119">Ezután a felső szintű kategória alatt létrehozott egyes kategóriákhoz rendelheti hozzá a termékeket.</span><span class="sxs-lookup"><span data-stu-id="c52df-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="c52df-120">Kategóriák sorrendjének testreszabása</span><span class="sxs-lookup"><span data-stu-id="c52df-120">Customize the order of categories</span></span>

<span data-ttu-id="c52df-121">Alapértelmezés szerint a megadott kategóriák ábécésorrendben jelennek meg a webhelyén.</span><span class="sxs-lookup"><span data-stu-id="c52df-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="c52df-122">Azonban a kategóriák megjelenítési sorrendjét is testreszabhatja.</span><span class="sxs-lookup"><span data-stu-id="c52df-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="c52df-123">Típus hozzárendelése kategóriahierarchiához </span><span class="sxs-lookup"><span data-stu-id="c52df-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="c52df-124">Ugorjon a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kategóriák és termékmenedzsment** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c52df-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="c52df-125">Válassza a **Kategóriahierarchiák** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="c52df-126">A műveleti ablaktáblán a **Kategóriahierarchia** lapon a **Beállítás** csoportban válassza a **Hierarchiatípus társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="c52df-127">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-127">Select **New**.</span></span>
1. <span data-ttu-id="c52df-128">A **Kategóriahierarchia-típus** mezőben válassza a **Csatornák navigációs hierarchiája** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="c52df-129">A **Kategóriahierarchia** mezőben válassza ki a korábban létrehozott csatornanavigációs hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="c52df-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="c52df-130">Új vagy frissített navigációs hierarchiák közzététele</span><span class="sxs-lookup"><span data-stu-id="c52df-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="c52df-131">Ha a navigációs hierarchiáját elérhetővé szeretné tenni az online kirakatában, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c52df-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="c52df-132">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.</span><span class="sxs-lookup"><span data-stu-id="c52df-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="c52df-133">Válassza ki az online áruházát a bal oldali fában.</span><span class="sxs-lookup"><span data-stu-id="c52df-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="c52df-134">Válassza a **Csatornafrissítések közzététele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c52df-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="c52df-135">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c52df-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="c52df-136">Keresse meg és válassza ki a listáról a **1040-es feladat** elemet.</span><span class="sxs-lookup"><span data-stu-id="c52df-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="c52df-137">Válassza a **Futtatás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c52df-137">Select **Run now**.</span></span>
1. <span data-ttu-id="c52df-138">Ismételje meg az 5. és 6. lépést az 1070-es és 1150-es feladatok esetében.</span><span class="sxs-lookup"><span data-stu-id="c52df-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="c52df-139">Kategóriák megjelenítése a webhelyen</span><span class="sxs-lookup"><span data-stu-id="c52df-139">Show categories on your site</span></span>

<span data-ttu-id="c52df-140">Ha meg szeretné jeleníteni a kategóriahierarchiát az online kirakatában, akkor egy sablon vagy töredék megfelelő helyén egy navigációs menü modult kell hozzáadnia.</span><span class="sxs-lookup"><span data-stu-id="c52df-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="c52df-141">A navigációs menü modul ezt követően megmutatja a navigációs hierarchiát, feltéve, hogy a navigációs hierarchiát közzétette a csatornán, amelyhez a webhelye hozzá van kötve.</span><span class="sxs-lookup"><span data-stu-id="c52df-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="c52df-142">Az áruház kezdőcsomagban található navigációs menü modul lehetővé teszi a felhasználók számára, hogy csak olyan kategóriákba navigáljanak, amelyeknél nincsenek alkategóriák.</span><span class="sxs-lookup"><span data-stu-id="c52df-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="c52df-143">Ha a vevők olyan kategóriákhoz szeretnének navigálni, amelyek rendelkeznek alkategóriákkal, akkor testre kell szabnia a navigációs menü modulját.</span><span class="sxs-lookup"><span data-stu-id="c52df-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="c52df-144">Egyéni navigációs beállítások hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c52df-144">Add custom navigation options</span></span>

<span data-ttu-id="c52df-145">A navigációs menüben hozzáadhat olyan navigációs beállításokat, amelyek nem szerepelnek a termék kategóriahierarchiájában.</span><span class="sxs-lookup"><span data-stu-id="c52df-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="c52df-146">A termékkategóriák listájának végén például hozzáadhat egy **Kapcsolat** elemet, amely egy kapcsolati információkat tartalmazó lapra mutat, amelyet a webhelyéhez állított össze.</span><span class="sxs-lookup"><span data-stu-id="c52df-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="c52df-147">A navigációs menü egyéni navigációs beállításainak hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c52df-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="c52df-148">Válassza ki a módosítani kívánt sablont vagy töredéket a navigációs menü modulban.</span><span class="sxs-lookup"><span data-stu-id="c52df-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="c52df-149">A tulajdonságlapon az **Adatok** fülön válassza az **Elem hozzáadása** lehetőséget egy új tartalomkezelő rendszer (CMS) navigációs elem létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c52df-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="c52df-150">Adja meg a hivatkozás szövegét és URL-címét.</span><span class="sxs-lookup"><span data-stu-id="c52df-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="c52df-151">További egyéni navigációs lehetőségek hozzáadásához ismételje meg a 2. és 3. lépést.</span><span class="sxs-lookup"><span data-stu-id="c52df-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="c52df-152">Ha végzett, mentse a sablont vagy a töredéket, és ellenőrizze, hogy be van-e adva.</span><span class="sxs-lookup"><span data-stu-id="c52df-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c52df-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c52df-153">Additional resources</span></span>

[<span data-ttu-id="c52df-154">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="c52df-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="c52df-155">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="c52df-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="c52df-156">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="c52df-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="c52df-157">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="c52df-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="c52df-158">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="c52df-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="c52df-159">Weblap URL-címének létrehozása</span><span class="sxs-lookup"><span data-stu-id="c52df-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="c52df-160">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="c52df-160">Work with publish groups</span></span>](publish-groups.md)
