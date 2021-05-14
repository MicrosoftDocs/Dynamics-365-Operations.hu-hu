---
title: Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz
description: Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920657"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="6afb0-103">Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="6afb0-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6afb0-104">Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="6afb0-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="6afb0-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6afb0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6afb0-106">Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="6afb0-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="6afb0-107">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="6afb0-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="6afb0-108">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="6afb0-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="6afb0-109">Ugorjon a **Termékinformációk kezelése \> Beállítás \> Termék elnevezési rendszere** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6afb0-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="6afb0-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-110">Select **New**.</span></span>
1. <span data-ttu-id="6afb0-111">A **Név** mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="6afb0-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="6afb0-112">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6afb0-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="6afb0-113">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-113">Select **Add**.</span></span>
1. <span data-ttu-id="6afb0-114">Válassza az **Alaptermék** számát.</span><span class="sxs-lookup"><span data-stu-id="6afb0-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="6afb0-115">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-115">Select **Add**.</span></span>
1. <span data-ttu-id="6afb0-116">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="6afb0-117">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6afb0-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6afb0-118">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-118">Select **Add**.</span></span>
1. <span data-ttu-id="6afb0-119">Válassza ki a **Szín** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-119">Select **Color**.</span></span>
1. <span data-ttu-id="6afb0-120">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-120">Select **Add**.</span></span>
1. <span data-ttu-id="6afb0-121">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="6afb0-122">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6afb0-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6afb0-123">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6afb0-123">Select **Add**.</span></span>
1. <span data-ttu-id="6afb0-124">Válassza a **Méret** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-124">Select **Size**.</span></span>
1. <span data-ttu-id="6afb0-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6afb0-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="6afb0-126">Rendelje hozzá az elnevezési rendszert az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="6afb0-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="6afb0-127">Válassza ki a **Termékdimenzió-csoportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="6afb0-128">Válassza ki a **SizeCol termékdimenzió-csoport** elemet.</span><span class="sxs-lookup"><span data-stu-id="6afb0-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="6afb0-129">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="6afb0-129">Select **Edit**.</span></span>
4. <span data-ttu-id="6afb0-130">Válassza az **Igen** lehetőséget az **Elnevezési rendszer használata** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6afb0-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="6afb0-131">A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6afb0-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="6afb0-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6afb0-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]