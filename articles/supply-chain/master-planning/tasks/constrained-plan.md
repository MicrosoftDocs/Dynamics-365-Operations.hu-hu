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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8b9d5712dd1b4f9958de775e1a2224b64485d05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429539"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="e0f02-103">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="e0f02-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0f02-104">Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="e0f02-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="e0f02-105">A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva.</span><span class="sxs-lookup"><span data-stu-id="e0f02-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="e0f02-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e0f02-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e0f02-107">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="e0f02-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="e0f02-108">Korlátozott terv beállítása</span><span class="sxs-lookup"><span data-stu-id="e0f02-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="e0f02-109">Válassza ki az **Alaptervezés** munkaterületet a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="e0f02-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="e0f02-110">Válassza ki az **Alapterveket** a munkaterület jobb szélén található hivatkozások listáján.</span><span class="sxs-lookup"><span data-stu-id="e0f02-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="e0f02-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e0f02-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="e0f02-112">Példa: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="e0f02-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="e0f02-113">Válassza az **Igen** lehetőséget a **Véges kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e0f02-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="e0f02-114">A **Végleges kapacitás időkorlátja** mezőbe, írja be: `30`.</span><span class="sxs-lookup"><span data-stu-id="e0f02-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="e0f02-115">Bontsa ki az **Időkorlátokat napokban** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e0f02-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="e0f02-116">Válassza az **Igen** lehetőséget a **Kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e0f02-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="e0f02-117">A **Kapacitásütemezési időkorlát (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="e0f02-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="e0f02-118">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="e0f02-118">Example: `60`</span></span>  
9. <span data-ttu-id="e0f02-119">Válassza ki az **Igen** lehetőséget a **Kiszámított késések** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e0f02-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="e0f02-120">A **Kiszámított késések időkorlátja (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="e0f02-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="e0f02-121">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="e0f02-121">Example: `60`</span></span> 
11. <span data-ttu-id="e0f02-122">A **Kiszámított késések** szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="e0f02-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="e0f02-123">Válassza ki az **Igen** lehetőséget az összes **Számított késés hozzáadása a követelménydátumhoz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e0f02-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="e0f02-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e0f02-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="e0f02-125">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="e0f02-125">Create a constrained plan</span></span>
1. <span data-ttu-id="e0f02-126">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e0f02-126">Select **Run**.</span></span>
2. <span data-ttu-id="e0f02-127">Az **Alapterv** mezőbe írja be vagy válassza ki azt a tervet, amelyhez be szeretné állítani a megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="e0f02-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="e0f02-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e0f02-128">Select **OK**.</span></span>
4. <span data-ttu-id="e0f02-129">**Tervezett rendelések** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="e0f02-129">Select **Planned orders**.</span></span>

