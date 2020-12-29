---
title: Vállalatközi terv létrehozása
description: Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet.
author: ShylaThompson
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ae3d8a7c437ffd41a4864bd8548aa84c8ab8f32
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429378"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="27f6e-103">Vállalatközi terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="27f6e-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27f6e-104">Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet.</span><span class="sxs-lookup"><span data-stu-id="27f6e-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="27f6e-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="27f6e-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="27f6e-106">Vállalatközi tervezőcsoport beállítása</span><span class="sxs-lookup"><span data-stu-id="27f6e-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="27f6e-107">A **Navigációs ablaktáblán** lépjen a **Modulok > Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="27f6e-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="27f6e-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="27f6e-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="27f6e-109">Például szűrjön a Név mezőben a „10” érték megadásával.</span><span class="sxs-lookup"><span data-stu-id="27f6e-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="27f6e-110">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="27f6e-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="27f6e-111">Kattintson a **Törlés** gombra.</span><span class="sxs-lookup"><span data-stu-id="27f6e-111">Click **Delete**.</span></span> <span data-ttu-id="27f6e-112">Ez a lépés szükséges a vállalatközi tervezési futtatás lerövidítéséhez.</span><span class="sxs-lookup"><span data-stu-id="27f6e-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="27f6e-113">A vállalatközi tervezés az tervezési csoport összes vállalatára lefuttatja az alaptervezést, a legalacsonyabb ütemezési sorrendtől kezdve.</span><span class="sxs-lookup"><span data-stu-id="27f6e-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="27f6e-114">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="27f6e-114">Click **Yes**.</span></span>
6. <span data-ttu-id="27f6e-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="27f6e-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="27f6e-116">Vállalatközi terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="27f6e-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="27f6e-117">A **Navigációs ablaktáblán** lépjen a **Modulok > Alaptervezés > Munkaterületek > Alaptervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="27f6e-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="27f6e-118">Kattintson a **Vállalatközi alaptervezés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="27f6e-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="27f6e-119">A **Vállalatközi tervezőcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="27f6e-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="27f6e-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="27f6e-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="27f6e-121">Válassza ki a 10. vállalatközi tervezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="27f6e-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="27f6e-122">A **Vállalatközi tervezési ismétlések száma** mezőbe írja be a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="27f6e-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="27f6e-123">A 10. vállalatközi tervezőcsoportnak két tagja van.</span><span class="sxs-lookup"><span data-stu-id="27f6e-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="27f6e-124">Annak érdekében, hogy propagálja a késedelmeket a forrásvállalattól (USMF) a vevő vállalathoz (DEMF), a vállalatközi két alkalommal kell lefuttatni, mindkét vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="27f6e-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="27f6e-125">Az első iteráció propagálja az igényt és azonosítja a késedelmeket a forrásvállalatnál (USMF).</span><span class="sxs-lookup"><span data-stu-id="27f6e-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="27f6e-126">A második iterációs propagálja a késedelmeket a USMF és a DEMF között.</span><span class="sxs-lookup"><span data-stu-id="27f6e-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="27f6e-127">Az **Első ismétlés** mezőben válassza az „Újbóli létrehozás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27f6e-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="27f6e-128">A **További ismétlések** mezőben válassza az „Újbóli létrehozás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27f6e-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="27f6e-129">Adjon meg egy számot a **Szálak száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="27f6e-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="27f6e-130">Ez a párhuzamos tervezésre használt szálak számát jelenti.</span><span class="sxs-lookup"><span data-stu-id="27f6e-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="27f6e-131">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27f6e-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="27f6e-132">A terv eredményének megtekintése</span><span class="sxs-lookup"><span data-stu-id="27f6e-132">View the result of the plan</span></span>
1. <span data-ttu-id="27f6e-133">A **Konstrukció** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="27f6e-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="27f6e-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="27f6e-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="27f6e-135">Kattintson a StaticPlan hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="27f6e-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="27f6e-136">A USMF vállalatban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="27f6e-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="27f6e-137">Kattintson a **Tervezett rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="27f6e-137">Click **Planned orders**.</span></span>

