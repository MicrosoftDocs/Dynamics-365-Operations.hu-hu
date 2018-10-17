--- 
title: "Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz"
description: "Ez az útmutató bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="0d8b4-103">Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="0d8b4-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d8b4-104">Ez az útmutató bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="0d8b4-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0d8b4-106">Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="0d8b4-107">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="0d8b4-108">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="0d8b4-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="0d8b4-109">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="0d8b4-110">Kattintson a Termékek elnevezési rendszere elemre</span><span class="sxs-lookup"><span data-stu-id="0d8b4-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="0d8b4-111">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-111">Click New.</span></span>
4. <span data-ttu-id="0d8b4-112">A Név mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például ColorSize.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="0d8b4-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="0d8b4-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-114">Click Add.</span></span>
7. <span data-ttu-id="0d8b4-115">Kattintson az Alaptermék száma elemre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-115">Click Product master number.</span></span>
8. <span data-ttu-id="0d8b4-116">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-116">Click Add.</span></span>
9. <span data-ttu-id="0d8b4-117">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-117">Click Text constant.</span></span>
10. <span data-ttu-id="0d8b4-118">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="0d8b4-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-119">Click Add.</span></span>
12. <span data-ttu-id="0d8b4-120">Kattintson a Szín lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-120">Click Color.</span></span>
13. <span data-ttu-id="0d8b4-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-121">Click Add.</span></span>
14. <span data-ttu-id="0d8b4-122">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-122">Click Text constant.</span></span>
15. <span data-ttu-id="0d8b4-123">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="0d8b4-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-124">Click Add.</span></span>
17. <span data-ttu-id="0d8b4-125">Kattintson a Méret lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-125">Click Size.</span></span>
18. <span data-ttu-id="0d8b4-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="0d8b4-127">Rendelje hozzá az elnevezési rendszert az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="0d8b4-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="0d8b4-128">Kattintson a Termékdimenzió-csoportokra.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="0d8b4-129">Válassza ki a SizeCol termékdimenzió-csoportot.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="0d8b4-130">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-130">Click Edit.</span></span>
4. <span data-ttu-id="0d8b4-131">Válassza az Igen lehetőséget az Elnevezési rendszer használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="0d8b4-132">A Termékváltozat-számozási rendszer mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="0d8b4-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0d8b4-133">Close the page.</span></span>


