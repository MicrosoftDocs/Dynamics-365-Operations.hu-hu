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
ms.openlocfilehash: d4af946a8dd4e5311bcb90386c88d5e7f205c4eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999856"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="dd212-103">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="dd212-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd212-104">Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="dd212-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="dd212-105">A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva.</span><span class="sxs-lookup"><span data-stu-id="dd212-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="dd212-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="dd212-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="dd212-107">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="dd212-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="dd212-108">Korlátozott terv beállítása</span><span class="sxs-lookup"><span data-stu-id="dd212-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="dd212-109">Válassza ki az **Alaptervezés** munkaterületet a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="dd212-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="dd212-110">Válassza ki az **Alapterveket** a munkaterület jobb szélén található hivatkozások listáján.</span><span class="sxs-lookup"><span data-stu-id="dd212-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="dd212-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="dd212-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="dd212-112">Példa: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="dd212-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="dd212-113">Válassza az **Igen** lehetőséget a **Véges kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd212-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="dd212-114">A **Végleges kapacitás időkorlátja** mezőbe, írja be: `30`.</span><span class="sxs-lookup"><span data-stu-id="dd212-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="dd212-115">Bontsa ki az **Időkorlátokat napokban** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd212-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="dd212-116">Válassza az **Igen** lehetőséget a **Kapacitás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd212-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="dd212-117">A **Kapacitásütemezési időkorlát (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="dd212-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="dd212-118">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="dd212-118">Example: `60`</span></span>  
9. <span data-ttu-id="dd212-119">Válassza ki az **Igen** lehetőséget a **Kiszámított késések** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd212-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="dd212-120">A **Kiszámított késések időkorlátja (napok)** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="dd212-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="dd212-121">Példa: `60`</span><span class="sxs-lookup"><span data-stu-id="dd212-121">Example: `60`</span></span> 
11. <span data-ttu-id="dd212-122">A **Kiszámított késések** szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="dd212-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="dd212-123">Válassza ki az **Igen** lehetőséget az összes **Számított késés hozzáadása a követelménydátumhoz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd212-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="dd212-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="dd212-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="dd212-125">Korlátozott terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="dd212-125">Create a constrained plan</span></span>
1. <span data-ttu-id="dd212-126">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="dd212-126">Select **Run**.</span></span>
2. <span data-ttu-id="dd212-127">Az **Alapterv** mezőbe írja be vagy válassza ki azt a tervet, amelyhez be szeretné állítani a megszorításokat.</span><span class="sxs-lookup"><span data-stu-id="dd212-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="dd212-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd212-128">Select **OK**.</span></span>
4. <span data-ttu-id="dd212-129">**Tervezett rendelések** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="dd212-129">Select **Planned orders**.</span></span>

