--- 
title: "Termékszám létrehozása előre definiált termékváltozatokhoz"
description: "Ez az útmutató bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="9fe72-103">Termékszám létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="9fe72-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9fe72-104">Ez az útmutató bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="9fe72-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="9fe72-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9fe72-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9fe72-106">Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="9fe72-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="9fe72-107">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="9fe72-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="9fe72-108">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="9fe72-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="9fe72-109">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="9fe72-110">Kattintson a Termékek elnevezési rendszere elemre</span><span class="sxs-lookup"><span data-stu-id="9fe72-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="9fe72-111">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-111">Click New.</span></span>
4. <span data-ttu-id="9fe72-112">A Név mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például ColorSize.</span><span class="sxs-lookup"><span data-stu-id="9fe72-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="9fe72-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9fe72-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="9fe72-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-114">Click Add.</span></span>
7. <span data-ttu-id="9fe72-115">Kattintson az Alaptermék száma elemre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-115">Click Product master number.</span></span>
8. <span data-ttu-id="9fe72-116">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-116">Click Add.</span></span>
9. <span data-ttu-id="9fe72-117">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-117">Click Text constant.</span></span>
10. <span data-ttu-id="9fe72-118">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9fe72-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="9fe72-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-119">Click Add.</span></span>
12. <span data-ttu-id="9fe72-120">Kattintson a Szín lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-120">Click Color.</span></span>
13. <span data-ttu-id="9fe72-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-121">Click Add.</span></span>
14. <span data-ttu-id="9fe72-122">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-122">Click Text constant.</span></span>
15. <span data-ttu-id="9fe72-123">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9fe72-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="9fe72-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-124">Click Add.</span></span>
17. <span data-ttu-id="9fe72-125">Kattintson a Méret lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-125">Click Size.</span></span>
18. <span data-ttu-id="9fe72-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9fe72-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="9fe72-127">Rendelje hozzá az elnevezési rendszert az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="9fe72-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="9fe72-128">Kattintson a Termékdimenzió-csoportokra.</span><span class="sxs-lookup"><span data-stu-id="9fe72-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="9fe72-129">Válassza ki a SizeCol termékdimenzió-csoportot.</span><span class="sxs-lookup"><span data-stu-id="9fe72-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="9fe72-130">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9fe72-130">Click Edit.</span></span>
4. <span data-ttu-id="9fe72-131">Válassza az Igen lehetőséget az Elnevezési rendszer használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="9fe72-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="9fe72-132">A Termékváltozat-számozási rendszer mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9fe72-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="9fe72-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9fe72-133">Close the page.</span></span>

