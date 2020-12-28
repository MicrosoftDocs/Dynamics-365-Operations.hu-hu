---
title: Változatcsoport létrehozása
description: Ez a témakör azt mutatja be, hogyan hozhat létre szín-, stílus- vagy színváltozat csoportot egy termékhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d9279e1076796bb455429e5ff004c89ec5829e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412860"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="dbdb6-103">Változatcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbdb6-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="dbdb6-104">Ez a témakör azt mutatja be, hogyan hozhat létre szín-, stílus- vagy színváltozat csoportot egy termékhez a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dbdb6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="dbdb6-105">Overview</span></span>

<span data-ttu-id="dbdb6-106">A Dynamics 365 Commerce támogatja a termékek több változatát.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="dbdb6-107">Ideális megoldás változatcsoportok beállítása a különböző termékkategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="dbdb6-108">Például méretcsoport hozható létre a az extrakicsi, kicsi, közepes, nagy, extranagy méretű pólókhoz, illetve színcsoportot is létre lehet hozni, amely tartalmazza a termék összes rendelkezésre álló színét.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="dbdb6-109">A termékek felvétele előtt kell hozzáadni a változatcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="dbdb6-110">Ebben a témakörben egy méretcsoportot hozunk létre és konfigurálunk.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="dbdb6-111">Hasonló eljárások használhatók a stílus- és színcsoportok hozzáadására és beállítására is.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="dbdb6-112">Méretcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbdb6-112">Create a size group</span></span>

<span data-ttu-id="dbdb6-113">Méretcsoport létrehozásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="dbdb6-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="dbdb6-114">A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Változatcsoportok \> Méretcsoportok**.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="dbdb6-115">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="dbdb6-116">A **Méretcsoport** mezőbe írjon be egy nevet a méretcsoportnak.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="dbdb6-117">Ha szükséges, akkor adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="dbdb6-118">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="dbdb6-119">Attribútumok hozzáadása a méretcsoporthoz</span><span class="sxs-lookup"><span data-stu-id="dbdb6-119">Add attributes to the size group</span></span>

<span data-ttu-id="dbdb6-120">Attribútum hozzáadásához egy méretcsoporthoz kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="dbdb6-121">A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Változatcsoportok \> Méretcsoportok**</span><span class="sxs-lookup"><span data-stu-id="dbdb6-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="dbdb6-122">A navigációs ablaktáblán válasszon egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="dbdb6-123">A **Méret csoport sorai** területen válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="dbdb6-124">A **Méret** mezőbe írjon be egy karakterláncot a mérethez (például „XL”).</span><span class="sxs-lookup"><span data-stu-id="dbdb6-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="dbdb6-125">A **Méret neve** mezőbe írja be a méret nevét (például „Extranagy”).</span><span class="sxs-lookup"><span data-stu-id="dbdb6-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="dbdb6-126">A **Feltöltési súly** mezőbe írjon be egy számot, amely a feltöltési súlyt jelenti.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="dbdb6-127">A **Vonalkódban lévő szám** mezőbe írjon be egy számot a vonalkódnak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="dbdb6-128">A **Megjelenítési sorrend** mezőbe a megjelenítési sorrendet jelölő számot.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="dbdb6-129">Ha befejezte a méretek hozzáadását, válassza a művelet ablaktábla **Mentés** elemét .</span><span class="sxs-lookup"><span data-stu-id="dbdb6-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="dbdb6-130">A következő kép egy példát mutat be az „utcai pólóméretek” méretcsoportjára.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Méretcsoport létrehozása](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="dbdb6-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbdb6-132">Additional resources</span></span>

[<span data-ttu-id="dbdb6-133">Termékek adatainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="dbdb6-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="dbdb6-134">Retail termékek beállítása</span><span class="sxs-lookup"><span data-stu-id="dbdb6-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="dbdb6-135">Termékdimenziók</span><span class="sxs-lookup"><span data-stu-id="dbdb6-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
