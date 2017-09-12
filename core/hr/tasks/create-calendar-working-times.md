--- 
title: "Naptár létrehozása és munkaidők generálása"
description: "A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d65fe0363e418f9c2e78bd78e802a4b0ea98599c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-calendar-and-generate-working-times"></a><span data-ttu-id="30498-103">Naptár létrehozása és munkaidők generálása</span><span class="sxs-lookup"><span data-stu-id="30498-103">Create a calendar and generate working times</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="30498-104">A naptárak írják le az üzemi erőforrásokhoz munkaidejét és kapacitását.</span><span class="sxs-lookup"><span data-stu-id="30498-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="30498-105">Ezzel az eljárással meghatározhat egy munkanaptárat egy munkaidősablon alapján.</span><span class="sxs-lookup"><span data-stu-id="30498-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="30498-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="30498-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="30498-107">Ugrás az összes munkaterületek > Erőforrás életciklusa kezelése elemre.</span><span class="sxs-lookup"><span data-stu-id="30498-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="30498-108">Kattintson a Naptárak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30498-108">Click Calendars.</span></span>
3. <span data-ttu-id="30498-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30498-109">Click New.</span></span>
4. <span data-ttu-id="30498-110">Írjon be egy értéket a Naptár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="30498-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="30498-111">Ez azon naptár azonosítója, amely referenciaként szolgál naptárak hozzárendelésekor például üzemi erőforrásokhoz vagy egy erőforráscsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="30498-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="30498-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="30498-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="30498-113">A Normál munkanap órákban mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="30498-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="30498-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="30498-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="30498-115">Kattintson a Munkaidők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30498-115">Click Working times.</span></span>
9. <span data-ttu-id="30498-116">Kattintson a Munkaidők összeállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30498-116">Click Compose working times.</span></span>
    * <span data-ttu-id="30498-117">Hozzon létre munkaórákat minden egyes naphoz abban az időszakban, amikorra a munkát akarja ütemezni.</span><span class="sxs-lookup"><span data-stu-id="30498-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="30498-118">Az idő előrehaladtával további időszakokhoz is létrehozhat munkaidőket.</span><span class="sxs-lookup"><span data-stu-id="30498-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="30498-119">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="30498-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="30498-120">Ez az első nap, amelyen ezt a naptárat ki kell nyitni.</span><span class="sxs-lookup"><span data-stu-id="30498-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="30498-121">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="30498-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="30498-122">Ez az utolsó nap, amelyen ez a naptár nyitva van.</span><span class="sxs-lookup"><span data-stu-id="30498-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="30498-123">A Minkaidősablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="30498-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="30498-124">A munkaidősablon határozza meg a munkaórákat a hét egyes napjain.</span><span class="sxs-lookup"><span data-stu-id="30498-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="30498-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="30498-125">Click OK.</span></span>
14. <span data-ttu-id="30498-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="30498-126">Close the page.</span></span>


