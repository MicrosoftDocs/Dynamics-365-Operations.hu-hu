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
ms.openlocfilehash: 8c69dc3f8e70c3b0a760f54d2251757ac997a432
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841623"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="a6b8a-103">Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="a6b8a-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a6b8a-104">Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="a6b8a-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a6b8a-106">Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="a6b8a-107">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="a6b8a-108">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="a6b8a-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="a6b8a-109">Válassza a **Termékváltozat modelldefiníciója** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="a6b8a-110">Válassza a **Termék elnevezési rendszere** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="a6b8a-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-111">Select **New**.</span></span>
4. <span data-ttu-id="a6b8a-112">A **Név** mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="a6b8a-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="a6b8a-114">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-114">Select **Add**.</span></span>
7. <span data-ttu-id="a6b8a-115">Válassza az **Alaptermék** számát.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="a6b8a-116">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-116">Select **Add**.</span></span>
9. <span data-ttu-id="a6b8a-117">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="a6b8a-118">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="a6b8a-119">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-119">Select **Add**.</span></span>
12. <span data-ttu-id="a6b8a-120">Válassza ki a **Szín** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-120">Select **Color**.</span></span>
13. <span data-ttu-id="a6b8a-121">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-121">Select **Add**.</span></span>
14. <span data-ttu-id="a6b8a-122">Válassza a **Szöveges állandó** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="a6b8a-123">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="a6b8a-124">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-124">Select **Add**.</span></span>
17. <span data-ttu-id="a6b8a-125">Válassza a **Méret** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-125">Select **Size**.</span></span>
18. <span data-ttu-id="a6b8a-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="a6b8a-127">Rendelje hozzá az elnevezési rendszert az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="a6b8a-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="a6b8a-128">Válassza ki a **Termékdimenzió-csoportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="a6b8a-129">Válassza ki a **SizeCol termékdimenzió-csoport** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="a6b8a-130">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-130">Select **Edit**.</span></span>
4. <span data-ttu-id="a6b8a-131">Válassza az **Igen** lehetőséget az **Elnevezési rendszer használata** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="a6b8a-132">A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="a6b8a-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-133">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]