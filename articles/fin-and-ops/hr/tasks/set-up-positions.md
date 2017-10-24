--- 
title: "Beosztások beállítása"
description: "A beosztások szervezeti hierarchia alacsonyabb szintjének fontos részei."
author: DarinKramer
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c902f532e189753a375d4b48edd9ef0b6d74020e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-positions"></a><span data-ttu-id="880f7-103">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="880f7-103">Set up positions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="880f7-104">A beosztások szervezeti hierarchia alacsonyabb szintjének fontos részei.</span><span class="sxs-lookup"><span data-stu-id="880f7-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="880f7-105">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="880f7-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="880f7-106">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek hozzárendelhetők az „Értékesítési igazgató” munkához.</span><span class="sxs-lookup"><span data-stu-id="880f7-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="880f7-107">Egy pozíció létezik a részlegen belül, és megtörténhet, hogy csak egy dolgozóval van társítva.</span><span class="sxs-lookup"><span data-stu-id="880f7-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="880f7-108">Ebben a feladatban a beosztás létrehozásához szükséges lépéseket mutatjuk be.</span><span class="sxs-lookup"><span data-stu-id="880f7-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="880f7-109">Ez az eljárás az emberi erőforrások szakértői számára alkalmas.</span><span class="sxs-lookup"><span data-stu-id="880f7-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="880f7-110">Kattintson a Munkaerő-kezelésre.</span><span class="sxs-lookup"><span data-stu-id="880f7-110">Click Workforce management.</span></span>
2. <span data-ttu-id="880f7-111">Kattintson a nyitott beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="880f7-111">Click Open positions.</span></span>
3. <span data-ttu-id="880f7-112">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="880f7-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="880f7-113">A Munka mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="880f7-114">A rendszer automatikusan másolja a kiválasztott munkakörből a pozícióba másolja a munkaköri leírást, a titulust és a teljes munkaidős helyettesítő foglalkoztatási tényezőt.</span><span class="sxs-lookup"><span data-stu-id="880f7-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="880f7-115">ResolveChanges a Feladat.</span><span class="sxs-lookup"><span data-stu-id="880f7-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="880f7-116">Kattintson a beosztás létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="880f7-116">Click Create position.</span></span>
7. <span data-ttu-id="880f7-117">A Részleg mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="880f7-118">A Beosztás típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="880f7-119">Az Kompenzációs régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="880f7-120">A kompenzációs régió mező meghatározza a kompenzáció alkalmazhatósági szabályait és a fix növekmény költségvetéseit, ami az adott pozícióban lévő alkalmazottra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="880f7-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="880f7-121">Az Elérhető hozzárendeléshez mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="880f7-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="880f7-122">Bontsa ki a Beosztás időtartama szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="880f7-123">A korábban beírt aktiválási és kivezetési dátumok alapján alapértelmezettként megadott beosztás időtartama</span><span class="sxs-lookup"><span data-stu-id="880f7-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="880f7-124">Bontsa ki a Jelentés a beosztásnak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="880f7-125">Ha hozzárendel egy dolgozót egy olyan pozícióhoz, amely egy másik pozícióhoz van rendelve, akkor közvetlen jelentési kapcsolatot hoz lére a két beosztáshoz rendelt dolgozó között.</span><span class="sxs-lookup"><span data-stu-id="880f7-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="880f7-126">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="880f7-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="880f7-127">A Jelentés a következőnek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="880f7-128">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="880f7-128">Click Create.</span></span>
16. <span data-ttu-id="880f7-129">Bontsa ki a Munkavállaló hozzárendelése szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="880f7-130">Bontsa ki a Kapcsolatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="880f7-131">Ha szervezete mátrix hierarchiát vagy egyéb egyéni hierarchiát alkalmaz, beállíthat pozíció hierarchia típusokat, majd hozzáadhat jelentési kapcsolatokat minden egyes beállított hierarchia típushoz.</span><span class="sxs-lookup"><span data-stu-id="880f7-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="880f7-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="880f7-132">Click Add.</span></span>
19. <span data-ttu-id="880f7-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="880f7-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="880f7-134">A Hierarchia neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="880f7-135">A Jelentés beosztás szerint mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="880f7-136">Bontsa ki a Bérlista szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="880f7-137">A Fizetési ciklus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="880f7-138">A Fizette: mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="880f7-139">Az Éves rendes munkaidő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="880f7-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="880f7-140">Ez a várhatóan évente betöltött beosztásban lévő dolgozó rendszeresen fizetett óráinak száma.</span><span class="sxs-lookup"><span data-stu-id="880f7-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="880f7-141">Bontsa ki a Szakszervezet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="880f7-142">Zárja be a Szakszervezet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="880f7-143">Bontsa ki a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="880f7-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="880f7-144">A Felosztási sablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="880f7-145">A Részleg mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="880f7-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="880f7-146">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="880f7-146">Click Save.</span></span>

