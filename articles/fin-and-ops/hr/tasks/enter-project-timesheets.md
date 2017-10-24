--- 
title: "Projekt időnyilvántartásának megadása"
description: "Ezen folyamat segítségével létrehozhat egy munkaidő-nyilvántartást egy üres munkaidő-nyilvántartási képernyő felhasználásával."
author: kherr75
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1f88fbbacde9c0bd2b3499df5682a717d0b804ab
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="enter-project-timesheets"></a><span data-ttu-id="3ed7c-103">Projekt időnyilvántartásának megadása</span><span class="sxs-lookup"><span data-stu-id="3ed7c-103">Enter project timesheets</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3ed7c-104">Ezen folyamat segítségével létrehozhat egy munkaidő-nyilvántartást egy üres munkaidő-nyilvántartási képernyő felhasználásával.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="3ed7c-105">Az új munkaidő-nyilvántartás egy előző munkaidő-nyilvántartás adatain, vagy a Kedvenceim oldalon található projekt- és tevékenység-hozzárendelések adatain alapulhat.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the My favourites page.</span></span> <span data-ttu-id="3ed7c-106">Alapértelmezés szerint az Összes munkaidő-nyilvántartás listaoldal minden munkaidő-nyilvántartást megjelenít az aktuális időszakra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-106">By default, the All timesheets list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="3ed7c-107">A Saját időnyilvántartások oldalon a Megjelenítés mező legördülő listája használható a munkaidő-nyilvántartások listájának szűrésére időszak vagy projekt alapján, vagy más munkavállalók nevében létrehozott időnyilvántartások megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-107">You can use the drop-down list for the Show field in the My timesheets page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="3ed7c-108">Ez az eljárás a USSI bemutatócéggel jött létre.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-108">The demo data company used to create this procedure is USSI.</span></span> <span data-ttu-id="3ed7c-109">Ennek az eljárásnak a megkezdéséhez ugorjon a Projektvezetési és könyvelési > Munkaidő-nyilvántartások > Saját időnyilvántartások pontra</span><span class="sxs-lookup"><span data-stu-id="3ed7c-109">To begin this procedure, go to Project management and accounting > Timesheets >My timesheets</span></span>

1. <span data-ttu-id="3ed7c-110">Új időnyilvántartás megadásához kattintson az Új gombra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-110">To enter a new timesheet, click New.</span></span>
    * <span data-ttu-id="3ed7c-111">Az Erőforrás legördülő lista alapértelmezés szerint megjeleníti az aktuális felhasználóhoz hozzárendelt dolgozót.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    * <span data-ttu-id="3ed7c-112">Ha a felhasználó delegáltnak van jelölve, a nevek felsorolásra kerülnek úgy, hogy a felhasználó a nevükben megadhat munkaidő-nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
2. <span data-ttu-id="3ed7c-113">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-113">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="3ed7c-114">Ha ez a beállítás ki van választva, új munkaidő-nyilvántartási sorok kerülnek létrehozásra kedvencként beállított munkaidő-nyilvántartási beállításokat felhasználva.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favourites.</span></span>  
3. <span data-ttu-id="3ed7c-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-115">Click OK.</span></span>
4. <span data-ttu-id="3ed7c-116">Kattintson az Új sor gombra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-116">Click New line.</span></span>
5. <span data-ttu-id="3ed7c-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3ed7c-118">A Jogi személy mező alapértelmezés szerint az aktuális Jogi személyt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-118">The Legal Entity field displays the current Legal entity by default.</span></span>   
6. <span data-ttu-id="3ed7c-119">A Projekt mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-119">In the Project field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="3ed7c-120">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="3ed7c-120">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="3ed7c-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="3ed7c-122">A Tevékenység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-122">In the Activity field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="3ed7c-123">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="3ed7c-123">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="3ed7c-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-124">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="3ed7c-125">A Kategória mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-125">In the Category field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="3ed7c-126">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="3ed7c-126">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="3ed7c-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-127">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="3ed7c-128">Adja meg az egyes napokon teljesített munkaórák számát.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-128">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="3ed7c-129">Az Órák beállítást decimális formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-129">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="3ed7c-130">Ha például két óra tizenöt percig dolgozott, akkor a 2,25 értéket írja be.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
16. <span data-ttu-id="3ed7c-131">Adja meg az egyes napokon teljesített munkaórák számát.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-131">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="3ed7c-132">Az Órák beállítást decimális formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-132">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="3ed7c-133">Ha például két óra tizenöt percig dolgozott, akkor a 2,25 értéket írja be.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-133">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="3ed7c-134">Adja meg az egyes napokon teljesített munkaórák számát.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-134">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="3ed7c-135">Az Órák beállítást decimális formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-135">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="3ed7c-136">Ha például két óra tizenöt percig dolgozott, akkor a 2,25 értéket írja be.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-136">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
18. <span data-ttu-id="3ed7c-137">Adja meg az egyes napokon teljesített munkaórák számát.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-137">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="3ed7c-138">Az Órák beállítást decimális formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-138">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="3ed7c-139">Ha például két óra tizenöt percig dolgozott, akkor a 2,25 értéket írja be.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-139">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
19. <span data-ttu-id="3ed7c-140">Adja meg az egyes napokon teljesített munkaórák számát.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-140">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="3ed7c-141">Az Órák beállítást decimális formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-141">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="3ed7c-142">Ha például két óra tizenöt percig dolgozott, akkor a 2,25 értéket írja be.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-142">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
    * <span data-ttu-id="3ed7c-143">A Soradatok menüben a következő beállítások közül lehet választani:  o  Adó és pénzügyi dimenziókhoz kapcsolódó adatok megadása.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-143">In Line details, the following options are available:  o  Add information about taxes and financial dimensions.</span></span>  <span data-ttu-id="3ed7c-144">o    A munkaidő-nyilvántartási sorra vonatkozó megjegyzések hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-144">o    Add comments about the timesheet line.</span></span>  
20. <span data-ttu-id="3ed7c-145">A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-145">Click Workflow to open the drop dialog.</span></span>
21. <span data-ttu-id="3ed7c-146">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-146">Click Submit.</span></span>
22. <span data-ttu-id="3ed7c-147">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ed7c-147">Click Submit.</span></span>

