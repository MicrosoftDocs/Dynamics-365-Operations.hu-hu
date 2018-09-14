--- 
title: "Vállalatközi terv létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d378a89bbb4de6d67db0019dc72a27945d50c4e9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="b308e-103">Vállalatközi terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="b308e-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b308e-104">Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet.</span><span class="sxs-lookup"><span data-stu-id="b308e-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="b308e-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b308e-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="b308e-106">Vállalatközi tervezőcsoport beállítása</span><span class="sxs-lookup"><span data-stu-id="b308e-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="b308e-107">Menjen a Vállalatközi tervezőcsoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="b308e-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="b308e-108">Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok</span><span class="sxs-lookup"><span data-stu-id="b308e-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="b308e-109">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="b308e-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="b308e-110">Például szűrjön a Név mezőben a „10” érték megadásával.</span><span class="sxs-lookup"><span data-stu-id="b308e-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="b308e-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b308e-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b308e-112">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="b308e-112">Click Delete.</span></span>
    * <span data-ttu-id="b308e-113">Ez a lépés szükséges a vállalatközi tervezési futtatás lerövidítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b308e-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="b308e-114">A vállalatközi tervezés az tervezési csoport összes vállalatára lefuttatja az alaptervezést, a legalacsonyabb ütemezési sorrendtől kezdve.</span><span class="sxs-lookup"><span data-stu-id="b308e-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="b308e-115">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="b308e-115">Click Yes.</span></span>
6. <span data-ttu-id="b308e-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b308e-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="b308e-117">Vállalatközi terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="b308e-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="b308e-118">Kattintson a Vállalatközi alaptervezés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b308e-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="b308e-119">Ez az Alaptervezés munkaterületen található.</span><span class="sxs-lookup"><span data-stu-id="b308e-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="b308e-120">A Vállalatközi tervezőcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b308e-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b308e-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b308e-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b308e-122">Válassza ki a 10. vállalatközi tervezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="b308e-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="b308e-123">A Vállalatközi tervezési ismétlések száma mezőbe írja be a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="b308e-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="b308e-124">A 10. vállalatközi tervezőcsoportnak két tagja van.</span><span class="sxs-lookup"><span data-stu-id="b308e-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="b308e-125">Annak érdekében, hogy propagálja a késedelmeket a forrásvállalattól (USMF) a vevő vállalathoz (DEMF), a vállalatközi két alkalommal kell lefuttatni, mindkét vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="b308e-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="b308e-126">Az első iteráció propagálja az igényt és azonosítja a késedelmeket a forrásvállalatnál (USMF).</span><span class="sxs-lookup"><span data-stu-id="b308e-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="b308e-127">A második iterációs propagálja a késedelmeket a USMF és a DEMF között.</span><span class="sxs-lookup"><span data-stu-id="b308e-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="b308e-128">Az Első ismétlés mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b308e-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="b308e-129">Az Első ismétlés mezőben válassza az „Újbóli létrehozás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b308e-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="b308e-130">A További ismétlések mezőben válassza az „Újbóli létrehozás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b308e-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="b308e-131">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="b308e-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="b308e-132">Ez a párhuzamos tervezésre használt szálak számát jelenti.</span><span class="sxs-lookup"><span data-stu-id="b308e-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="b308e-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b308e-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="b308e-134">A terv eredményének megtekintése</span><span class="sxs-lookup"><span data-stu-id="b308e-134">View the result of the plan</span></span>
1. <span data-ttu-id="b308e-135">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b308e-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="b308e-136">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b308e-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b308e-137">Kattintson a StaticPlan hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="b308e-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="b308e-138">A USMF vállalatban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b308e-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="b308e-139">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="b308e-139">Click Planned orders.</span></span>


