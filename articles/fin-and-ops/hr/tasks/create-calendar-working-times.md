---
title: Naptár létrehozása és munkaidők generálása
description: A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a556367857890acdb926ed29518cf2f2f2b92ea
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "336014"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="eeaa3-103">Naptár létrehozása és munkaidők generálása</span><span class="sxs-lookup"><span data-stu-id="eeaa3-103">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eeaa3-104">A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="eeaa3-105">Ezzel az eljárással meghatározhat egy munkanaptárat egy munkaidősablon alapján.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="eeaa3-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="eeaa3-107">Ugrás az összes munkaterületek > Erőforrás életciklusa kezelése elemre.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="eeaa3-108">Kattintson a Naptárak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-108">Click Calendars.</span></span>
3. <span data-ttu-id="eeaa3-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-109">Click New.</span></span>
4. <span data-ttu-id="eeaa3-110">Írjon be egy értéket a Naptár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="eeaa3-111">Ez azon naptár azonosítója, amely referenciaként szolgál naptárak hozzárendelésekor például üzemi erőforrásokhoz vagy egy erőforráscsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="eeaa3-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="eeaa3-113">A Normál munkanap órákban mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="eeaa3-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="eeaa3-115">Kattintson a Munkaidők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-115">Click Working times.</span></span>
9. <span data-ttu-id="eeaa3-116">Kattintson a Munkaidők összeállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-116">Click Compose working times.</span></span>
    * <span data-ttu-id="eeaa3-117">Hozzon létre munkaórákat minden egyes naphoz abban az időszakban, amikorra a munkát akarja ütemezni.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="eeaa3-118">Az idő előrehaladtával további időszakokhoz is létrehozhat munkaidőket.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="eeaa3-119">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="eeaa3-120">Ez az első nap, amelyen ezt a naptárat ki kell nyitni.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="eeaa3-121">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="eeaa3-122">Ez az utolsó nap, amelyen ez a naptár nyitva van.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="eeaa3-123">A Minkaidősablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="eeaa3-124">A munkaidősablon határozza meg a munkaórákat a hét egyes napjain.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="eeaa3-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-125">Click OK.</span></span>
14. <span data-ttu-id="eeaa3-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eeaa3-126">Close the page.</span></span>

