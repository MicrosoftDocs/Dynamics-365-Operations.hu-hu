---
title: Naptárak létrehozása és munkaidők generálása
description: A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását. Ez a témakör bemutatja, hogyan definiálhat egy munkanaptárat egy munkaidősablon alapján.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50b81ae228d9aee4111ce8d161508d5ed1af4f27
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738996"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="32a14-104">Naptár létrehozása és munkaidők generálása</span><span class="sxs-lookup"><span data-stu-id="32a14-104">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32a14-105">A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását.</span><span class="sxs-lookup"><span data-stu-id="32a14-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="32a14-106">Ez a témakör bemutatja, hogyan definiálhat egy munkanaptárat egy munkaidősablon alapján.</span><span class="sxs-lookup"><span data-stu-id="32a14-106">This topic explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="32a14-107">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="32a14-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="32a14-108">A kezdőlapon válassza az **Erőforrás életcikluskezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="32a14-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="32a14-109">Válassza a **Naptárak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="32a14-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="32a14-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="32a14-110">Select **New**.</span></span>
4. <span data-ttu-id="32a14-111">A **Naptár** mezőben osztályozza a naptárát.</span><span class="sxs-lookup"><span data-stu-id="32a14-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="32a14-112">Ez azon naptár azonosítója, amely referenciaként szolgál naptárak hozzárendelésekor például üzemi erőforrásokhoz vagy egy erőforráscsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="32a14-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="32a14-113">A **Név** mezőben adjon meg egy nevet a naptárnak.</span><span class="sxs-lookup"><span data-stu-id="32a14-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="32a14-114">A **Normál munkanap órákban** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="32a14-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="32a14-115">Ellenőrizze, hogy a sor ki van-e jelölve, majd válassza a **Munkaidők** beállítást a műveletpanelen.</span><span class="sxs-lookup"><span data-stu-id="32a14-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="32a14-116">Válasza a **Munkaidők felépítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="32a14-116">Select **Compose working times**.</span></span> <span data-ttu-id="32a14-117">Hozzon létre munkaórákat minden egyes naphoz abban az időszakban, amikorra a munkát akarja ütemezni.</span><span class="sxs-lookup"><span data-stu-id="32a14-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="32a14-118">Az idő előrehaladtával további időszakokhoz is létrehozhat munkaidőket.</span><span class="sxs-lookup"><span data-stu-id="32a14-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="32a14-119">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="32a14-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="32a14-120">Ez az első nap, amelyen ezt a naptárat ki kell nyitni.</span><span class="sxs-lookup"><span data-stu-id="32a14-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="32a14-121">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="32a14-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="32a14-122">Ez az utolsó nap, amelyen ez a naptár nyitva van.</span><span class="sxs-lookup"><span data-stu-id="32a14-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="32a14-123">A **Munkaidősablon** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="32a14-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="32a14-124">A munkaidősablon határozza meg a munkaórákat a hét egyes napjain.</span><span class="sxs-lookup"><span data-stu-id="32a14-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="32a14-125">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="32a14-125">Select **OK**.</span></span>
13. <span data-ttu-id="32a14-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="32a14-126">Close the page.</span></span>

