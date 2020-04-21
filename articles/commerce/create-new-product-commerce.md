---
title: Új termék létrehozása Commerce-ben
description: Ez a témakör azt mutatja be, hogyan lehet új terméket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: eb2dd36c6149f2aa40305cd57eac060b232b09e5
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138561"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="b2365-103">Új termék létrehozása Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="b2365-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b2365-104">Ez a témakör azt mutatja be, hogyan lehet új terméket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b2365-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b2365-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b2365-105">Overview</span></span>

<span data-ttu-id="b2365-106">A terméket elsősorban a termékszáma, a neve és a leírása határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b2365-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="b2365-107">Azonban más adatokra is szükség van egy termék vagy egy szolgáltatás leírásához:</span><span class="sxs-lookup"><span data-stu-id="b2365-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="b2365-108">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2365-108">Create a new product</span></span>

1. <span data-ttu-id="b2365-109">A Navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Termékek kategóriák szerint**.</span><span class="sxs-lookup"><span data-stu-id="b2365-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="b2365-110">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b2365-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b2365-111">A **Termék típusa** legördülő listában válassza a **Cikk** vagy a **Szolgáltatás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b2365-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="b2365-112">A **Termék altípusa** legördülő listában válassza a **Termék** (ha a termék nem tartalmaz változatokat) vagy az **Alaptermék** (ha a terméknek vannak változatai) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="b2365-113">A **Termékszám** mezőbe írjon be egy termékszámot ha még nincs előzetesen kitöltve.</span><span class="sxs-lookup"><span data-stu-id="b2365-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="b2365-114">A **Termék neve** mezőbe írjon be egy terméknevet.</span><span class="sxs-lookup"><span data-stu-id="b2365-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="b2365-115">A **Keresési név** mezőbe írjon be egy keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="b2365-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="b2365-116">A **Kiskereskedelmi kategória** legördülő listából válassza ki a megfelelő kategóriát.</span><span class="sxs-lookup"><span data-stu-id="b2365-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="b2365-117">Ha a termék egy készlet , válassza az **Igen** lehetőséget a **Termékkészlet** alatt.</span><span class="sxs-lookup"><span data-stu-id="b2365-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="b2365-118">Ha a termék altípusa alaptermék, akkor a **Termék dimenzióját** állítsa be, hogy tartalmazza a támogatott változatokat.</span><span class="sxs-lookup"><span data-stu-id="b2365-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="b2365-119">A lehetőségek többek között a **Szín**, **Méret**, **Stílus** és **Konfiguráció**.</span><span class="sxs-lookup"><span data-stu-id="b2365-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="b2365-120">Szükség esetén előfordulhat, hogy további cikkdimenzió-csoportokat kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="b2365-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="b2365-121">A **Konfigurációkategória** legördülő listából válassza ki a megfelelő beállítást.</span><span class="sxs-lookup"><span data-stu-id="b2365-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="b2365-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-122">Select **OK**.</span></span>

<span data-ttu-id="b2365-123">A következő képen egy példaként hozzáadott termék jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b2365-123">The following image shows an example product being added.</span></span>

![Termék létrehozása](media/create-new-product.png)

<span data-ttu-id="b2365-125">A termék hozzáadását követően további adatok is megadhatók, például a **Termék leírása**, **Változatcsoportok**, **Dimenziócsoportok**, **Termékattribútumok** és **Kapcsolódó termékek**.</span><span class="sxs-lookup"><span data-stu-id="b2365-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="b2365-126">A következő kép egy termék további részleteit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b2365-126">The following image shows a product's additional details.</span></span>

![Termék részletei](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="b2365-128">Termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2365-128">Create product variants</span></span>

<span data-ttu-id="b2365-129">Ha a termék altípusa **Alaptermék**, akkor konkrét változatokat kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="b2365-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="b2365-130">Termékváltozatok létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b2365-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="b2365-131">A művelet ablaktáblán válassza ki a **Termékváltozatok** elemet.</span><span class="sxs-lookup"><span data-stu-id="b2365-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="b2365-132">Ha a műveleti ablaktáblában változatcsoportok lettek kiválasztva, válassza a \**Változatjavaslatok* elemet.</span><span class="sxs-lookup"><span data-stu-id="b2365-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="b2365-133">Válassza ki a termékhez támogatandó változatokat.</span><span class="sxs-lookup"><span data-stu-id="b2365-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="b2365-134">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="b2365-135">Egy termék kiadása</span><span class="sxs-lookup"><span data-stu-id="b2365-135">Release a product</span></span>

<span data-ttu-id="b2365-136">A termék értékesítéséhez először egy jogi személynek ki kell adni azt.</span><span class="sxs-lookup"><span data-stu-id="b2365-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="b2365-137">A termék lapon válassza ki a **Termékek kiadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-137">From the product page, select **Release products**.</span></span>

    ![Termék kiadása](media/create-new-product-3.png)

1. <span data-ttu-id="b2365-139">Válassza ki a kiadni kívánt terméket, majd kattintsona **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2365-139">Select the product to release, and then select **Next**.</span></span>

    ![Válasszon egy terméket kiadásra](media/create-new-product-4.png)

1. <span data-ttu-id="b2365-141">Válassza ki a kiadni kívánt termékváltozatok készletét, majd kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2365-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Változatok kiválasztása kiadásra](media/create-new-product-5.png)

1. <span data-ttu-id="b2365-143">Válassza ki a jogi személyt, majd kattintsona **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2365-143">Select the legal entity, and then select **Next**.</span></span>

    ![Jogi személy kiválasztása](media/create-new-product-6.png)

1. <span data-ttu-id="b2365-145">Válassza a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-145">Select **Finish**.</span></span>

    ![Termékkiadás befejezése](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="b2365-147">Egy kiadott termék konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b2365-147">Configure a released product</span></span>

<span data-ttu-id="b2365-148">Egy termék kiadása után a rendszer további konfigurációt igényel, amely tartalmazza az ár hozzáadását a termékhez.</span><span class="sxs-lookup"><span data-stu-id="b2365-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="b2365-149">A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Kiadott termékek kategóriák szerint**.</span><span class="sxs-lookup"><span data-stu-id="b2365-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="b2365-150">Válassza ki a termék kategóriájának csomópontját a kiadott termékhez, majd válassza ki a terméket a listából.</span><span class="sxs-lookup"><span data-stu-id="b2365-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="b2365-151">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="b2365-152">A **Beszerzés** szakaszban konfigurálja a szükséges tulajdonságokat, többek között az **Egységet**, az **Árat** és a **Mennyiséget**.</span><span class="sxs-lookup"><span data-stu-id="b2365-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="b2365-153">A műveleti panelen jelölje be az **Ellenőrzés** jelölőnégyzetet, hogy a hiányzó mezők esetében ne jelentsen a rendszer hibát.</span><span class="sxs-lookup"><span data-stu-id="b2365-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="b2365-154">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2365-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b2365-155">A következő kép egy példát mutat egy kiadott termék beállítási konfigurációjáról.</span><span class="sxs-lookup"><span data-stu-id="b2365-155">The following image shows an example configuration for a released product.</span></span>

![Kiadott termék konfigurálása](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="b2365-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b2365-157">Additional resources</span></span>

[<span data-ttu-id="b2365-158">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2365-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="b2365-159">Változatcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2365-159">Create a variant group</span></span>](create-variant-group.md) 