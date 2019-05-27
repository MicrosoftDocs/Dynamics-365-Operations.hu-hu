---
title: Korlátozott terv létrehozása
description: Ez az eljárás bemutatja, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556023"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="3fe02-103">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="3fe02-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fe02-104">Ez az eljárás bemutatja, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="3fe02-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="3fe02-105">A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva.</span><span class="sxs-lookup"><span data-stu-id="3fe02-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="3fe02-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3fe02-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3fe02-107">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="3fe02-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="3fe02-108">Korlátozott terv beállítása</span><span class="sxs-lookup"><span data-stu-id="3fe02-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="3fe02-109">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="3fe02-109">Click Master planning.</span></span>
2. <span data-ttu-id="3fe02-110">Kattintson az Alaptervek parancsra.</span><span class="sxs-lookup"><span data-stu-id="3fe02-110">Click Master plans.</span></span>
3. <span data-ttu-id="3fe02-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3fe02-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3fe02-112">Példa: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="3fe02-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="3fe02-113">Válassza az Igen lehetőséget a Véges kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="3fe02-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="3fe02-114">A Végleges kapacitás időkorlátja mezőbe, írja be: '30'.</span><span class="sxs-lookup"><span data-stu-id="3fe02-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="3fe02-115">Bontsa ki az Időkorlátokat a napok szakaszában.</span><span class="sxs-lookup"><span data-stu-id="3fe02-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="3fe02-116">Válassza az Igen lehetőséget a Kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="3fe02-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="3fe02-117">A Kapacitásütemezési időkorlát (napok) mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="3fe02-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3fe02-118">Példa: 60</span><span class="sxs-lookup"><span data-stu-id="3fe02-118">Example: 60</span></span>  
9. <span data-ttu-id="3fe02-119">Válassza ki az Igen lehetőséget a Kiszámított késések mezőben.</span><span class="sxs-lookup"><span data-stu-id="3fe02-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="3fe02-120">A Kiszámított késések időkorlátja (napok) mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="3fe02-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3fe02-121">Példa: 60</span><span class="sxs-lookup"><span data-stu-id="3fe02-121">Example: 60</span></span>  
11. <span data-ttu-id="3fe02-122">A Kiszámított késések szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="3fe02-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="3fe02-123">Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben</span><span class="sxs-lookup"><span data-stu-id="3fe02-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="3fe02-124">Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben</span><span class="sxs-lookup"><span data-stu-id="3fe02-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="3fe02-125">Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben</span><span class="sxs-lookup"><span data-stu-id="3fe02-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="3fe02-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fe02-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="3fe02-127">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="3fe02-127">Create a constrained plan</span></span>
1. <span data-ttu-id="3fe02-128">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="3fe02-128">Click Run.</span></span>
2. <span data-ttu-id="3fe02-129">Az Alapterv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3fe02-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="3fe02-130">Válassza ki azt a tervet, amelyhez megszorítások állított be.</span><span class="sxs-lookup"><span data-stu-id="3fe02-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="3fe02-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3fe02-131">Click OK.</span></span>
    * <span data-ttu-id="3fe02-132">Ez eltarthat egy ideig.</span><span class="sxs-lookup"><span data-stu-id="3fe02-132">This may take a while.</span></span>  
4. <span data-ttu-id="3fe02-133">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="3fe02-133">Click Planned orders.</span></span>

