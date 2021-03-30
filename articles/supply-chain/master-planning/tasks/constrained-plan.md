---
title: Korlátozott terv létrehozása
description: Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d238ffd7ee76dcb782931312a132545a89f537b5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214394"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="ee0be-103">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="ee0be-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee0be-104">Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="ee0be-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="ee0be-105">A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva.</span><span class="sxs-lookup"><span data-stu-id="ee0be-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="ee0be-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ee0be-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ee0be-107">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="ee0be-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="ee0be-108">Korlátozott terv beállítása</span><span class="sxs-lookup"><span data-stu-id="ee0be-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="ee0be-109">Válassza ki az **Alaptervezés** munkaterületet a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="ee0be-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="ee0be-110">Válassza ki az **Alapterveket** a munkaterület jobb szélén található hivatkozások listáján.</span><span class="sxs-lookup"><span data-stu-id="ee0be-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="ee0be-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ee0be-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="ee0be-112">Példa: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="ee0be-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="ee0be-113">Válassza az **Igen** lehetőséget a **Véges kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ee0be-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="ee0be-114">A **Végleges kapacitás időkorlátja** mezőbe, írja be: `30`.</span><span class="sxs-lookup"><span data-stu-id="ee0be-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="ee0be-115">Bontsa ki az **Időkorlátokat napokban** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ee0be-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="ee0be-116">Válassza az **Igen** lehetőséget a **Kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ee0be-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="ee0be-117">A **Kapacitásütemezési időkorlát (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="ee0be-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="ee0be-118">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="ee0be-118">Example: `60`</span></span>  
9. <span data-ttu-id="ee0be-119">Válassza ki az **Igen** lehetőséget a **Kiszámított késések** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ee0be-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="ee0be-120">A **Kiszámított késések időkorlátja (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="ee0be-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="ee0be-121">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="ee0be-121">Example: `60`</span></span> 
11. <span data-ttu-id="ee0be-122">A **Kiszámított késések** szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="ee0be-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="ee0be-123">Válassza ki az **Igen** lehetőséget az összes **Számított késés hozzáadása a követelménydátumhoz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ee0be-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="ee0be-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ee0be-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="ee0be-125">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="ee0be-125">Create a constrained plan</span></span>
1. <span data-ttu-id="ee0be-126">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ee0be-126">Select **Run**.</span></span>
2. <span data-ttu-id="ee0be-127">Az **Alapterv** mezőbe írja be vagy válassza ki azt a tervet, amelyhez be szeretné állítani a megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="ee0be-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="ee0be-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0be-128">Select **OK**.</span></span>
4. <span data-ttu-id="ee0be-129">**Tervezett rendelések** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="ee0be-129">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]