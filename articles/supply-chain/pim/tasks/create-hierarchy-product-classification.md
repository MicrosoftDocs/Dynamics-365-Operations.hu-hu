---
title: A termékosztályozási hierarchia létrehozása
description: Ez az eljárás bemutatja, hogyan lehet új kategóriahierarchiát létrehozni, és ahhoz hozzárendelni a vámtarifakódok hierarchia-típusát.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb49f5f3f8a5a788cb4c6d1be69534ba808e3675
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "346824"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="ed271-103">A termékosztályozási hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed271-103">Create a hierarchy of product classification</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ed271-104">Ez az eljárás bemutatja, hogyan lehet új kategóriahierarchiát létrehozni, és ahhoz hozzárendelni a vámtarifakódok hierarchia-típusát.</span><span class="sxs-lookup"><span data-stu-id="ed271-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="ed271-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ed271-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ed271-106">Ezt az eljárást a kategóriavezető használja.</span><span class="sxs-lookup"><span data-stu-id="ed271-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="ed271-107">Az új kategóriahierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed271-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="ed271-108">Ugorjon a Termékinformációk kezelése > Beállítás > Kategóriák és attribútumok > Kategóriahierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="ed271-108">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="ed271-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ed271-109">Click New.</span></span>
3. <span data-ttu-id="ed271-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ed271-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ed271-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ed271-112">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ed271-112">Click Create.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="ed271-113">Hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed271-113">Build the hierarchy</span></span>
1. <span data-ttu-id="ed271-114">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="ed271-114">Click New category node.</span></span>
2. <span data-ttu-id="ed271-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-115">In the Name field, type a value.</span></span>
3. <span data-ttu-id="ed271-116">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="ed271-116">In the Code field, type a value.</span></span>
4. <span data-ttu-id="ed271-117">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-117">In the Friendly name field, type a value.</span></span>
5. <span data-ttu-id="ed271-118">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="ed271-118">Click New category node.</span></span>
6. <span data-ttu-id="ed271-119">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-119">In the Name field, type a value.</span></span>
7. <span data-ttu-id="ed271-120">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="ed271-120">In the Code field, type a value.</span></span>
8. <span data-ttu-id="ed271-121">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-121">In the Friendly name field, type a value.</span></span>
9. <span data-ttu-id="ed271-122">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="ed271-122">Click New category node.</span></span>
10. <span data-ttu-id="ed271-123">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-123">In the Name field, type a value.</span></span>
11. <span data-ttu-id="ed271-124">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="ed271-124">In the Code field, type a value.</span></span>
12. <span data-ttu-id="ed271-125">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-125">In the Friendly name field, type a value.</span></span>
13. <span data-ttu-id="ed271-126">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="ed271-126">Click New category node.</span></span>
14. <span data-ttu-id="ed271-127">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-127">In the Name field, type a value.</span></span>
15. <span data-ttu-id="ed271-128">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="ed271-128">In the Code field, type a value.</span></span>
16. <span data-ttu-id="ed271-129">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ed271-129">In the Friendly name field, type a value.</span></span>
17. <span data-ttu-id="ed271-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ed271-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="ed271-131">Hierarchia osztályozása</span><span class="sxs-lookup"><span data-stu-id="ed271-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="ed271-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ed271-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="ed271-133">A Műveleti ablakban kattintson a Kategóriahierarchia elemre.</span><span class="sxs-lookup"><span data-stu-id="ed271-133">On the Action Pane, click Category hierarchy.</span></span>
3. <span data-ttu-id="ed271-134">Kattintson a Hierarchiatípus társítása elemre.</span><span class="sxs-lookup"><span data-stu-id="ed271-134">Click Associate hierarchy type.</span></span>
4. <span data-ttu-id="ed271-135">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ed271-135">Click New.</span></span>
5. <span data-ttu-id="ed271-136">A Kategóriahierarchia típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ed271-136">In the Category hierarchy type field, select an option.</span></span>
    * <span data-ttu-id="ed271-137">A termékosztályozáshoz válassza ki az Árucikk kódjának kategóriahierarchia-típusát.</span><span class="sxs-lookup"><span data-stu-id="ed271-137">Select the Commodity code category hierarchy type for product classification.</span></span>  
6. <span data-ttu-id="ed271-138">A Kategóriahierarchia mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ed271-138">In the Category hierarchy field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ed271-139">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ed271-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ed271-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ed271-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ed271-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ed271-141">Close the page.</span></span>

