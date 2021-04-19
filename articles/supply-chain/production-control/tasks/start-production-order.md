---
title: Termelési rendelés indítása
description: Ezzel az eljárással lehet megkezdeni egy termelési rendelést az üzemirányítással.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be1c389bc4193ef080dbeb1639b69acf466ef0de
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831866"
---
# <a name="start-a-production-order"></a><span data-ttu-id="51640-103">Termelési rendelés indítása</span><span class="sxs-lookup"><span data-stu-id="51640-103">Start a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51640-104">Ezzel az eljárással lehet megkezdeni egy termelési rendelést az üzemirányítással.</span><span class="sxs-lookup"><span data-stu-id="51640-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="51640-105">Ebben a folyamatban jelentheti az idő- és nyersanyag-felhasználást.</span><span class="sxs-lookup"><span data-stu-id="51640-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="51640-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="51640-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="51640-107">Ez az ötödik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="51640-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="51640-108">Termelési rendelés indítása</span><span class="sxs-lookup"><span data-stu-id="51640-108">Start a production order</span></span>
1. <span data-ttu-id="51640-109">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="51640-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="51640-110">Válasszon ki egy Kiadott állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="51640-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="51640-111">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="51640-112">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-112">Click Start.</span></span>
    * <span data-ttu-id="51640-113">Ezen a lapon erősítse meg a termelési rendelés kezdetét.</span><span class="sxs-lookup"><span data-stu-id="51640-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="51640-114">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="51640-114">Click the General tab.</span></span>
5. <span data-ttu-id="51640-115">A Kezdő műveletben.</span><span class="sxs-lookup"><span data-stu-id="51640-115">In the From Oper.</span></span> <span data-ttu-id="51640-116">Szám</span><span class="sxs-lookup"><span data-stu-id="51640-116">No.</span></span> <span data-ttu-id="51640-117">mezőbe írja be a 10 értéket.</span><span class="sxs-lookup"><span data-stu-id="51640-117">field, enter '10'.</span></span>
6. <span data-ttu-id="51640-118">Az automatikus útvonal-felhasználás mezőben válassza ki ezt: „Mindig”.</span><span class="sxs-lookup"><span data-stu-id="51640-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="51640-119">Jelölje be az Útvonalkártya feladása most jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="51640-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="51640-120">Az automatikus BOM-felhasználás mezőben válassza ki ezt: „Mindig”.</span><span class="sxs-lookup"><span data-stu-id="51640-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="51640-121">Kattintson a Kitárolási lista feladása most jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="51640-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="51640-122">Kattintson a Kitárolási lista nyomtatása jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="51640-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="51640-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="51640-123">Click OK.</span></span>
    * <span data-ttu-id="51640-124">Ez az a nyomtatott kitárolási lista, amely a termelési rendeléshez felhasznált anyagokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="51640-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="51640-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="51640-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="51640-126">Kitárolási lista érvényesítése</span><span class="sxs-lookup"><span data-stu-id="51640-126">Validate the picking list</span></span>
1. <span data-ttu-id="51640-127">A Művelet panelen kattintson a Nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="51640-128">Kattintson a Kitárolási lista elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-128">Click Picking list.</span></span>
3. <span data-ttu-id="51640-129">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="51640-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="51640-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="51640-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="51640-131">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="51640-131">Click Edit.</span></span>
6. <span data-ttu-id="51640-132">Adjon meg egy számot a Fogyasztás mezőben.</span><span class="sxs-lookup"><span data-stu-id="51640-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="51640-133">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="51640-133">Click Post.</span></span>
8. <span data-ttu-id="51640-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="51640-134">Click OK.</span></span>
    * <span data-ttu-id="51640-135">A kitárolásilista-naplóban a program feladja a termelési rendeléshez felhasznált anyagokat.</span><span class="sxs-lookup"><span data-stu-id="51640-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="51640-136">A napló feladása előtt kiigazíthatja a becsült mennyiség és a tényleges felhasznált mennyiség közötti eltérést.</span><span class="sxs-lookup"><span data-stu-id="51640-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="51640-137">Kattintson a GridPanel fülre.</span><span class="sxs-lookup"><span data-stu-id="51640-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="51640-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="51640-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="51640-139">Az útvonalkártya-napló ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="51640-139">Verify the route card journal</span></span>
1. <span data-ttu-id="51640-140">A Művelet panelen kattintson a Nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="51640-141">Kattintson az Útvonalkártya elemre.</span><span class="sxs-lookup"><span data-stu-id="51640-141">Click Route card.</span></span>
3. <span data-ttu-id="51640-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="51640-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="51640-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="51640-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="51640-144">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="51640-144">Click Edit.</span></span>
6. <span data-ttu-id="51640-145">Adjon meg egy számot az Órák mezőben.</span><span class="sxs-lookup"><span data-stu-id="51640-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="51640-146">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="51640-146">Click Post.</span></span>
8. <span data-ttu-id="51640-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="51640-147">Click OK.</span></span>
    * <span data-ttu-id="51640-148">Az Útvonalkártya-naplóban rögzítheti az egyes műveletekkel töltött időt.</span><span class="sxs-lookup"><span data-stu-id="51640-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="51640-149">A jó és a hibás mennyiséget is jelenteni kell.</span><span class="sxs-lookup"><span data-stu-id="51640-149">Good and error quantity can also be reported.</span></span>  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]