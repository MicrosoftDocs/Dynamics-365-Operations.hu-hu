--- 
title: "Társtermékek anyagfelhasználási tervének létrehozása"
description: "A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ce34c-103">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce34c-103">Create a material plan for co-products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ce34c-104">A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.</span><span class="sxs-lookup"><span data-stu-id="ce34c-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="ce34c-105">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ce34c-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="ce34c-106">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce34c-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="ce34c-107">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="ce34c-108">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="ce34c-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="ce34c-109">Click New.</span></span>
4. <span data-ttu-id="ce34c-110">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-110">Click Sales order.</span></span>
5. <span data-ttu-id="ce34c-111">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce34c-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="ce34c-112">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="ce34c-112">Example: US-001</span></span>  
6. <span data-ttu-id="ce34c-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-113">Click OK.</span></span>
7. <span data-ttu-id="ce34c-114">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ce34c-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ce34c-115">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="ce34c-115">Example: P6003</span></span>  
8. <span data-ttu-id="ce34c-116">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce34c-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ce34c-117">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="ce34c-117">Example: 50000</span></span>  
9. <span data-ttu-id="ce34c-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ce34c-119">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce34c-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="ce34c-120">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-120">Click Master planning.</span></span>
2. <span data-ttu-id="ce34c-121">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ce34c-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ce34c-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ce34c-123">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="ce34c-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="ce34c-124">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="ce34c-124">Click Run.</span></span>
5. <span data-ttu-id="ce34c-125">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="ce34c-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="ce34c-126">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-126">Click Filter.</span></span>
7. <span data-ttu-id="ce34c-127">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="ce34c-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="ce34c-128">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce34c-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ce34c-129">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="ce34c-129">Example: P6003</span></span>  
9. <span data-ttu-id="ce34c-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-130">Click OK.</span></span>
10. <span data-ttu-id="ce34c-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-131">Click OK.</span></span>
11. <span data-ttu-id="ce34c-132">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="ce34c-132">Click Planned orders.</span></span>
12. <span data-ttu-id="ce34c-133">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="ce34c-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ce34c-134">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="ce34c-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="ce34c-135">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="ce34c-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="ce34c-136">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="ce34c-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ce34c-137">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="ce34c-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="ce34c-138">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="ce34c-139">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ce34c-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="ce34c-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ce34c-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ce34c-141">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="ce34c-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="ce34c-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ce34c-142">Close the page.</span></span>


