--- 
title: "Termelési rendelés ütemezése"
description: "Ez az eljárás bemutatja, hogyan lehet termelési rendelést ütemezni."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4aeb51fd2d9e916d5838b47c4a6b74800572a9ca
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-a-production-order"></a><span data-ttu-id="6fef1-103">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="6fef1-103">Schedule a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6fef1-104">Ez az eljárás bemutatja, hogyan lehet termelési rendelést ütemezni.</span><span class="sxs-lookup"><span data-stu-id="6fef1-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="6fef1-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6fef1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6fef1-106">Ez a harmadik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="6fef1-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="6fef1-107">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="6fef1-107">Schedule a production order</span></span>
1. <span data-ttu-id="6fef1-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="6fef1-109">Válasszon ki egy Becsült állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="6fef1-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="6fef1-110">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="6fef1-111">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="6fef1-112">Az ütemezéshez beállított paramétereket ezen az oldalon állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="6fef1-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="6fef1-113">Beállíthatja a paramétereket adott felhasználók, vagy az összes felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="6fef1-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="6fef1-114">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előrefelé” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6fef1-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="6fef1-115">Adjon meg egy dátumot az Ütemezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6fef1-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="6fef1-116">Jelölje be a Véges kapacitás jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="6fef1-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="6fef1-117">Jelölje be a Véges anyag jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="6fef1-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="6fef1-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6fef1-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="6fef1-119">Ütemezési eredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="6fef1-119">View the scheduling results</span></span>
1. <span data-ttu-id="6fef1-120">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="6fef1-121">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-121">Click All jobs.</span></span>
    * <span data-ttu-id="6fef1-122">Ezen a lapon láthatók a nemrég létrehozott ütemezett feladatokat.</span><span class="sxs-lookup"><span data-stu-id="6fef1-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="6fef1-123">Bontsa ki vagy csukja össze az Ütemezés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6fef1-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="6fef1-124">Az Ütemezés gyorslapon megtekintheti az ütemezett dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="6fef1-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="6fef1-125">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-125">Click Inquiries.</span></span>
5. <span data-ttu-id="6fef1-126">Kattintson a Kapacitásterhelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6fef1-126">Click Capacity load.</span></span>
    * <span data-ttu-id="6fef1-127">A Terhelési kapacitás lap megjeleníti, hogy milyen kapacitást foglalt le a feladat ütemezésén keresztül, az erőforráson jelenleg lefoglalt órák összes számát, illetve a fennmaradó az erőforrás a feladat ütemezéséhez még rendelkezésre álló óráinak a számát.</span><span class="sxs-lookup"><span data-stu-id="6fef1-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="6fef1-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6fef1-128">Close the page.</span></span>
7. <span data-ttu-id="6fef1-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6fef1-129">Close the page.</span></span>


