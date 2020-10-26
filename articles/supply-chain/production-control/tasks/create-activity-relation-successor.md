---
title: Tevékenységkapcsolat létrehozása – Követő
description: Lean termelési folyamat esetén a tevékenységek folyamata tevékenységkapcsolatokon keresztül kerül dokumentálásra.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91e1535ab6b53ad60394967d0377606a0cd27d01
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983446"
---
# <a name="create-activity-relation---successor"></a><span data-ttu-id="267fa-103">Tevékenységkapcsolat létrehozása – Követő</span><span class="sxs-lookup"><span data-stu-id="267fa-103">Create activity relation - Successor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="267fa-104">Lean termelési folyamat esetén a tevékenységek folyamata tevékenységkapcsolatokon keresztül kerül dokumentálásra.</span><span class="sxs-lookup"><span data-stu-id="267fa-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="267fa-105">Ez a felvétel bemutatja, hogyan hozhat létre tevékenységkapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="267fa-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="267fa-106">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="267fa-106">Prerequisites:</span></span>

- <span data-ttu-id="267fa-107">Termelési folyamat és verzió vázlat módban.</span><span class="sxs-lookup"><span data-stu-id="267fa-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="267fa-108">Két olyan tevékenység, amelyek követik egymást a termelési folyamatban létrejött ugyan, de nem kapcsolódnak egymáshoz.</span><span class="sxs-lookup"><span data-stu-id="267fa-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="267fa-109">Termelési folyamat verziójának megkeresése</span><span class="sxs-lookup"><span data-stu-id="267fa-109">Find the production flow version</span></span> 
1. <span data-ttu-id="267fa-110">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="267fa-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="267fa-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="267fa-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="267fa-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="267fa-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="267fa-113">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="267fa-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="267fa-114">Válasszon egy vázlatverziót a listából.</span><span class="sxs-lookup"><span data-stu-id="267fa-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="267fa-115">A tevékenységi kapcsolatok a termelési folyamat során a vázlatokhoz és az aktív verziókhoz is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="267fa-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="267fa-116">Tevékenység áttekintésének megnyitása</span><span class="sxs-lookup"><span data-stu-id="267fa-116">Open the activity overview</span></span>
1. <span data-ttu-id="267fa-117">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="267fa-117">Click Activities.</span></span>
    * <span data-ttu-id="267fa-118">Vegye figyelembe, hogy a képernyő a termelési folyamat minden olyan tevékenységét megjeleníti, amely az Ön által használt termelési folyamatok verziójához tartozik.</span><span class="sxs-lookup"><span data-stu-id="267fa-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="267fa-119">Követő hozzáadása</span><span class="sxs-lookup"><span data-stu-id="267fa-119">Add a Successor</span></span>
1. <span data-ttu-id="267fa-120">Kattintson a Követő hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="267fa-120">Click Add successor.</span></span>
2. <span data-ttu-id="267fa-121">A Tevékenység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="267fa-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="267fa-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="267fa-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="267fa-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="267fa-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="267fa-124">Jelölje be a Megszorítás jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="267fa-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="267fa-125">Adjon meg egy számot a Megszorítás értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="267fa-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="267fa-126">A megszorítási idő a megelőző ütemezett vége (lejárati dátum és idő) és a követő ütemezett kezdete között ütemezendő idő.</span><span class="sxs-lookup"><span data-stu-id="267fa-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="267fa-127">Írjon be egy értéket az Egységek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="267fa-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="267fa-128">Írjon be egy számot a Ciklusidőarány mezőbe.</span><span class="sxs-lookup"><span data-stu-id="267fa-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="267fa-129">Ha mindkét tevékenység ugyanazon taktidőben fut, a ciklusidő aránya kötelezően 1.</span><span class="sxs-lookup"><span data-stu-id="267fa-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="267fa-130">Ha a megelőző a követő tevékenység dupla sebességével fut, az arány kötelezően 2.</span><span class="sxs-lookup"><span data-stu-id="267fa-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="267fa-131">A termelési folyamat tevékenységeihez tartozó egyedi ciklusidők kiszámításához a ciklusidő-arányokat használjuk.</span><span class="sxs-lookup"><span data-stu-id="267fa-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="267fa-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="267fa-132">Click OK.</span></span>
10. <span data-ttu-id="267fa-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="267fa-133">Close the page.</span></span>
11. <span data-ttu-id="267fa-134">Kattintson a GridPanel fülre.</span><span class="sxs-lookup"><span data-stu-id="267fa-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="267fa-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="267fa-135">Close the page.</span></span>
13. <span data-ttu-id="267fa-136">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="267fa-136">Refresh the page.</span></span>

