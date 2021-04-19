---
title: Csatorna navigációs hierarchiájának létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet csatornanavigációs hierarchiát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 358f3d40c7a21184c20da342d6b2bf72dd4e7bbd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795835"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="91078-103">Csatorna navigációs hierarchiájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="91078-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="91078-104">Ez a témakör azt mutatja be, hogyan lehet csatornanavigációs hierarchiát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="91078-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="91078-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="91078-105">Overview</span></span>

<span data-ttu-id="91078-106">A csatornanavigációs hierarchiák csoportosítják kategóriákba rendezik a termékeket, így a termékek böngészhetők online vagy az pénztárakban (POS).</span><span class="sxs-lookup"><span data-stu-id="91078-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="91078-107">Csatorna navigációs hierarchiájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="91078-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="91078-108">Csatorna navigációs hierarchiájának létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="91078-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="91078-109">A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Csatornanavigációs kategóriák**.</span><span class="sxs-lookup"><span data-stu-id="91078-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="91078-110">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="91078-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="91078-111">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="91078-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="91078-112">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="91078-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="91078-113">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-113">Select **Create**.</span></span>
1. <span data-ttu-id="91078-114">Válassza műveleti ablakban az **Új kategóriacsomópont** lehetőséget a gyökércsomópont létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="91078-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="91078-115">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="91078-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="91078-116">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="91078-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="91078-117">A **Rövid neve** mezőbe írjon be egy rövid nevet.</span><span class="sxs-lookup"><span data-stu-id="91078-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="91078-118">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="91078-119">A következő képen egy gyökércsomópont példája látható.</span><span class="sxs-lookup"><span data-stu-id="91078-119">The following image shows a example root node.</span></span>

![Minta gyökércsomópont](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="91078-121">Navigációskategória-csomópontok létrehozása</span><span class="sxs-lookup"><span data-stu-id="91078-121">Create navigation category nodes</span></span>

<span data-ttu-id="91078-122">További navigációskategória-csomópontok létrehozásához a csatornán szereplő termékkategóriák megjelenítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="91078-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="91078-123">A navigációs ablakban válassza ki azt a szülő csomópontot, amelyhez kategóriát szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="91078-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="91078-124">A Műveleti ablaktáblában kattintson a **Új kategória-csomópont** elemre.</span><span class="sxs-lookup"><span data-stu-id="91078-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="91078-125">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="91078-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="91078-126">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="91078-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="91078-127">A **Rövid neve** mezőbe írjon be egy rövid nevet.</span><span class="sxs-lookup"><span data-stu-id="91078-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="91078-128">A **Megjelenítési sorrend** mezőbe adja meg megjelenítési sorrendet (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="91078-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="91078-129">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="91078-130">A következő kép egy példát mutat be egy elkészített csatorna navigációs hierarchiára.</span><span class="sxs-lookup"><span data-stu-id="91078-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Minta csatornahierarchia](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="91078-132">Termékek hozzáadása a kategóriacsomópontokhoz</span><span class="sxs-lookup"><span data-stu-id="91078-132">Add products to category nodes</span></span>

<span data-ttu-id="91078-133">Termékek hozzáadásához a kategóriacsomópontokhoz hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="91078-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="91078-134">Válasszon egy kategóriacsomópontot.</span><span class="sxs-lookup"><span data-stu-id="91078-134">Select a category node.</span></span>
1. <span data-ttu-id="91078-135">A **Termékek** alatt válassz a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="91078-136">Keresse meg a hozzáadni kívánt új termékeket a termékszámmal vagy a terméknévvel, majd válasszaaz **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="91078-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="91078-137">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="91078-138">A termékeket a csatorna navigációs hierarchiáján belül egy csomóponthoz való hozzáadása, nem elegendő ahhoz, hogy a termékek egy kiválasztott csatornán megjelenjenek, a termékeket hozzá kell társítani egy termékhez is.</span><span class="sxs-lookup"><span data-stu-id="91078-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="91078-139">A következő képen egy csomópont példája láható, hozzáadott termékekkel.</span><span class="sxs-lookup"><span data-stu-id="91078-139">The following image shows an example node with products added.</span></span>

![Termékek hozzáadva egy kategóriacsomóponthoz](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="91078-141">Termékattribútumok-csoportok hozzáadása a kategóriacsomópontjokhoz</span><span class="sxs-lookup"><span data-stu-id="91078-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="91078-142">Az attribútumok csoportját létre kell hozni ahhoz, hogy a csatorna navigációs hierarchiáján belül csomóponthoz adja hozzá azokat.</span><span class="sxs-lookup"><span data-stu-id="91078-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="91078-143">A következő lépésekkel lehet hozzáadni egy attribútumcsoportot egy kategóriacsomóponthoz.</span><span class="sxs-lookup"><span data-stu-id="91078-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="91078-144">Válasszon egy kategóriacsomópontot.</span><span class="sxs-lookup"><span data-stu-id="91078-144">Select a category node.</span></span>
1. <span data-ttu-id="91078-145">Válassza a **Termékattribútuma-csoport** **Hozzáadás** elemét.</span><span class="sxs-lookup"><span data-stu-id="91078-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="91078-146">Keresse meg azokat az attribútumcsoportokat, amelyeket hozzá szeretne adni, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="91078-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="91078-147">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91078-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="91078-148">A következő képen egy csomópontminta láható, hozzáadott termékattribútum-csoportokkal.</span><span class="sxs-lookup"><span data-stu-id="91078-148">The following image shows a sample node with product attribute groups added.</span></span>

![Termékattribútum-csoportok egy csomóponton](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="91078-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="91078-150">Additional resources</span></span>

[<span data-ttu-id="91078-151">Szortimentek beállítása</span><span class="sxs-lookup"><span data-stu-id="91078-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="91078-152">Attribútumok és attribútumcsoportok kezelése</span><span class="sxs-lookup"><span data-stu-id="91078-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]