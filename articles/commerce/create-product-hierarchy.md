---
title: Új termékhierarchia létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új termékhierarchiát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 73cecb0c6aacebf5c6fcf8a0edbc7513b3ce175d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001898"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="cf713-103">Új termékhierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="cf713-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="cf713-104">Ez a témakör azt mutatja be, hogyan lehet új termékhierarchiát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cf713-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cf713-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cf713-105">Overview</span></span>

<span data-ttu-id="cf713-106">A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát.</span><span class="sxs-lookup"><span data-stu-id="cf713-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="cf713-107">Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek).</span><span class="sxs-lookup"><span data-stu-id="cf713-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="cf713-108">A kiskereskedelmi üzletek csatornái saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="cf713-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="cf713-109">Az összes ilyen elemet be kell állítania, kiskereskedelmi üzlet csatornájának létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="cf713-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="cf713-110">A Commerce termékhierarchiája használatos a szervezet kiskereskedelmi termékhierarchiájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="cf713-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="cf713-111">A Commerce termékhierarchiáját használhatja árusítási, árképzési és promóciók, jelentések és a szortiment tervezési használható.</span><span class="sxs-lookup"><span data-stu-id="cf713-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="cf713-112">Csak egy Commerce termékhierarchia rendelhető hozzá szervezetenként.</span><span class="sxs-lookup"><span data-stu-id="cf713-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="cf713-113">Termékhierarchia létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cf713-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="cf713-114">Commerce termékhierarchia létrehozásához és konfigurálásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cf713-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="cf713-115">A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Commerce termékhierarchia**.</span><span class="sxs-lookup"><span data-stu-id="cf713-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="cf713-116">Ha még nincs hierarchia, akkor a **Műveleti ablaktáblán** válassza az **Új** lehetőséget a hierarchia gyökerének létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="cf713-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="cf713-117">Az **Általános** alatt:</span><span class="sxs-lookup"><span data-stu-id="cf713-117">Under **General**:</span></span>
    1. <span data-ttu-id="cf713-118">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="cf713-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="cf713-119">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cf713-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="cf713-120">A **Rövid neve** mezőbe írjon be egy rövid nevet.</span><span class="sxs-lookup"><span data-stu-id="cf713-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="cf713-121">Az **Aktív** elemet állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cf713-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="cf713-122">Hierarchia-csomópontok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cf713-122">Add hierarchy nodes</span></span>

<span data-ttu-id="cf713-123">Hierarchiacsomópontok hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cf713-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="cf713-124">A Műveleti ablaktáblában kattintson a **Kategóriahierarchia szerkesztése** elemre.</span><span class="sxs-lookup"><span data-stu-id="cf713-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="cf713-125">Válassza ki azt a szülőtartomány-csomópontot, amelyhez hozzá szeretné adni az új csomópontot, majd válassza ki az **Új kategória-csomópont** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf713-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="cf713-126">Az **Általános** szakaszban adja meg a **Név**, **Leírás**, **Rövid név** és **Kulcsszavak** adatokat.</span><span class="sxs-lookup"><span data-stu-id="cf713-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="cf713-127">Az **Általános** alatt:</span><span class="sxs-lookup"><span data-stu-id="cf713-127">Under **General**:</span></span>
    1. <span data-ttu-id="cf713-128">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="cf713-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="cf713-129">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cf713-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="cf713-130">A **Rövid neve** mezőbe írjon be egy rövid nevet.</span><span class="sxs-lookup"><span data-stu-id="cf713-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="cf713-131">A **Kulcsszavak** mezőbe írja be a megfelelő kulcsszavakat.</span><span class="sxs-lookup"><span data-stu-id="cf713-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="cf713-132">A **Megjelenítési sorrend** mezőbe a megjelenítési sorrendet jelölő számot (opcionális).</span><span class="sxs-lookup"><span data-stu-id="cf713-132">In the **Display order**box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="cf713-133">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf713-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="cf713-134">További csomópontok hozzáadásához ismételje meg a fenti lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cf713-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="cf713-135">A következő kép bemutatja egy új termékhierarchia-csomópont létrehozását.</span><span class="sxs-lookup"><span data-stu-id="cf713-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Termékhierarchia létrehozása](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="cf713-137">Egyéb beállítások</span><span class="sxs-lookup"><span data-stu-id="cf713-137">Other settings</span></span>

<span data-ttu-id="cf713-138">A kategória-attribútumok csoportjait igény szerint is hozzá lehet rendelni az egyes csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="cf713-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="cf713-139">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cf713-139">Additional resources</span></span>

[<span data-ttu-id="cf713-140">Kiskereskedelmi hierarchiák</span><span class="sxs-lookup"><span data-stu-id="cf713-140">Retail hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="cf713-141">Termékkategóriák és termékek kezelése </span><span class="sxs-lookup"><span data-stu-id="cf713-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="cf713-142">Árusítási entitások rendezési sorrendjének módosítása</span><span class="sxs-lookup"><span data-stu-id="cf713-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)