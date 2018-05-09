--- 
title: "A termékosztályozási hierarchia létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet új kategóriahierarchiát létrehozni, és ahhoz hozzárendelni a vámtarifakódok hierarchia-típusát."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 93ad9888f37c90057de93aa8f328d77bcf626a3c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="5ba93-103">A termékosztályozási hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="5ba93-103">Create a hierarchy of product classification</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ba93-104">Ez az eljárás bemutatja, hogyan lehet új kategóriahierarchiát létrehozni, és ahhoz hozzárendelni a vámtarifakódok hierarchia-típusát.</span><span class="sxs-lookup"><span data-stu-id="5ba93-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="5ba93-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5ba93-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="5ba93-106">Ezt az eljárást a kategóriavezető használja.</span><span class="sxs-lookup"><span data-stu-id="5ba93-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="5ba93-107">Az új kategóriahierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="5ba93-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="5ba93-108">Ugorjon a Termékinformációk kezelése > Beállítás > Kategóriák és attribútumok > Kategóriahierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-108">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="5ba93-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ba93-109">Click New.</span></span>
3. <span data-ttu-id="5ba93-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="5ba93-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ba93-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5ba93-112">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ba93-112">Click Create.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="5ba93-113">Hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="5ba93-113">Build the hierarchy</span></span>
1. <span data-ttu-id="5ba93-114">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-114">Click New category node.</span></span>
2. <span data-ttu-id="5ba93-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-115">In the Name field, type a value.</span></span>
3. <span data-ttu-id="5ba93-116">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="5ba93-116">In the Code field, type a value.</span></span>
4. <span data-ttu-id="5ba93-117">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-117">In the Friendly name field, type a value.</span></span>
5. <span data-ttu-id="5ba93-118">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-118">Click New category node.</span></span>
6. <span data-ttu-id="5ba93-119">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-119">In the Name field, type a value.</span></span>
7. <span data-ttu-id="5ba93-120">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="5ba93-120">In the Code field, type a value.</span></span>
8. <span data-ttu-id="5ba93-121">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-121">In the Friendly name field, type a value.</span></span>
9. <span data-ttu-id="5ba93-122">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-122">Click New category node.</span></span>
10. <span data-ttu-id="5ba93-123">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-123">In the Name field, type a value.</span></span>
11. <span data-ttu-id="5ba93-124">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="5ba93-124">In the Code field, type a value.</span></span>
12. <span data-ttu-id="5ba93-125">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-125">In the Friendly name field, type a value.</span></span>
13. <span data-ttu-id="5ba93-126">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-126">Click New category node.</span></span>
14. <span data-ttu-id="5ba93-127">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-127">In the Name field, type a value.</span></span>
15. <span data-ttu-id="5ba93-128">Írjon be egy értéket a Kód mezőbe</span><span class="sxs-lookup"><span data-stu-id="5ba93-128">In the Code field, type a value.</span></span>
16. <span data-ttu-id="5ba93-129">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ba93-129">In the Friendly name field, type a value.</span></span>
17. <span data-ttu-id="5ba93-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5ba93-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="5ba93-131">Hierarchia osztályozása</span><span class="sxs-lookup"><span data-stu-id="5ba93-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="5ba93-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5ba93-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="5ba93-133">A Műveleti ablakban kattintson a Kategóriahierarchia elemre.</span><span class="sxs-lookup"><span data-stu-id="5ba93-133">On the Action Pane, click Category hierarchy.</span></span>
3. <span data-ttu-id="5ba93-134">Kattintson a Hierarchiatípus társítása elemre.</span><span class="sxs-lookup"><span data-stu-id="5ba93-134">Click Associate hierarchy type.</span></span>
4. <span data-ttu-id="5ba93-135">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ba93-135">Click New.</span></span>
5. <span data-ttu-id="5ba93-136">A Kategóriahierarchia típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5ba93-136">In the Category hierarchy type field, select an option.</span></span>
    * <span data-ttu-id="5ba93-137">A termékosztályozáshoz válassza ki az Árucikk kódjának kategóriahierarchia-típusát.</span><span class="sxs-lookup"><span data-stu-id="5ba93-137">Select the Commodity code category hierarchy type for product classification.</span></span>  
6. <span data-ttu-id="5ba93-138">A Kategóriahierarchia mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5ba93-138">In the Category hierarchy field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5ba93-139">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="5ba93-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="5ba93-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5ba93-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5ba93-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5ba93-141">Close the page.</span></span>


