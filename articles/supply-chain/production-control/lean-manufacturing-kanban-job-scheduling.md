---
title: "Kanbanfeladat ütemezése lean manufacturing céljára"
description: "Ez a cikk a kanban-feladat ütemezés feletti vizuális ellenőrzésről és a kanban-feladatok ütemezésének különböző módszereiről nyújt tájékoztatást."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a8b2949fde28d83968f45535a5c47f263efbb18f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="kanban-job-scheduling-for-lean-manufacturing"></a><span data-ttu-id="04df4-103">Kanbanfeladat ütemezése lean manufacturing céljára</span><span class="sxs-lookup"><span data-stu-id="04df4-103">Kanban job scheduling for lean manufacturing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="04df4-104">Ez a cikk a kanban-feladat ütemezés feletti vizuális ellenőrzésről és a kanban-feladatok ütemezésének különböző módszereiről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="04df4-104">This article provides information about visual control over kanban job scheduling and various ways to schedule kanban jobs.</span></span>  

<span data-ttu-id="04df4-105">A **Kanbanfeladat ütemezése** oldal a lean manufacturing munkacellák ütemezéseinek vizuális ellenőrzésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="04df4-105">The **Kanban job scheduling** page provides visual control over the schedules of lean manufacturing work cells.</span></span> <span data-ttu-id="04df4-106">Áttekintheti az összes kanbanfeladatot és szűréseket végezhet számos különféle módon.</span><span class="sxs-lookup"><span data-stu-id="04df4-106">It gives an overview of all kanban jobs and provides multiple filtering capabilities.</span></span> <span data-ttu-id="04df4-107">Erről az oldalról lehetősége van minden más, kanbanok konfigurálásával és végrehajtásával kapcsolatos oldalra átváltani.</span><span class="sxs-lookup"><span data-stu-id="04df4-107">From this page, you can move to all other pages that are related to kanban configuration and execution.</span></span>

## <a name="automatic-scheduling-of-kanban-jobs"></a><span data-ttu-id="04df4-108">Kanbanfeladatok automatikus ütemezése</span><span class="sxs-lookup"><span data-stu-id="04df4-108">Automatic scheduling of kanban jobs</span></span>
<span data-ttu-id="04df4-109">Az ütemezés indítása akkor történhet automatikusan, ha a kanbanszabályhoz megadja az **Automatikus tervezési mennyiség** paramétert.</span><span class="sxs-lookup"><span data-stu-id="04df4-109">Scheduling can be triggered automatically if you set the **Automatic planning quantity** parameter on the kanban rule.</span></span> <span data-ttu-id="04df4-110">Amennyiben az **Automatikus tervezési mennyiség** értéke **1**, az egyes kanbanfeladatok a létrehozás után azonnal tervezetté válnak.</span><span class="sxs-lookup"><span data-stu-id="04df4-110">If you set **Automatic planning quantity** to **1**, each kanban job is planned immediately when it's created.</span></span> <span data-ttu-id="04df4-111">Az eredmény egy műveletekből álló sorozat, amelynek végrehajtása a lekérés sorrendjében történik.</span><span class="sxs-lookup"><span data-stu-id="04df4-111">The result is a series of first pull, first serve operations.</span></span> <span data-ttu-id="04df4-112">Amennyiben az **Automatikus tervezési mennyiség** értéke 1-nél nagyobb, a rendszer a tervezés előtt csoportosítja a kanbanfeladatokat.</span><span class="sxs-lookup"><span data-stu-id="04df4-112">If you set **Automatic planning quantity** to a value that is more than 1, kanban jobs are grouped before they are planned.</span></span> 

<span data-ttu-id="04df4-113">Ez a koncepció lehetővé teszi, hogy a kanbanok méretét a tényleges gazdaságos kötegméret alá csökkentsük.</span><span class="sxs-lookup"><span data-stu-id="04df4-113">This concept enables kanban sizes to be reduced below the actual economic batch sizes.</span></span> <span data-ttu-id="04df4-114">Tegyük fel például, hogy egy adott cikk (vagy egy cikkcsalád) gazdaságos kötegmérete 30.</span><span class="sxs-lookup"><span data-stu-id="04df4-114">For example, the economic batch size for a specific item (or item family) is 30.</span></span> <span data-ttu-id="04df4-115">Ez esetben 30-as termékmennyiséget használó kanbanok létrehozása helyett úgy is konfigurálhatja a kanbanszabályt, hogy a termék mennyisége 10, az **Automatikus tervezési mennyiség** pedig **3** legyen.</span><span class="sxs-lookup"><span data-stu-id="04df4-115">Instead of creating kanbans that use the product quantity, 30, you can configure the kanban rule so that it has a product quantity of 10 and an **Automatic planning quantity** value of **3**.</span></span> <span data-ttu-id="04df4-116">Bár az automatikus tervezés csak akkor ütemezi a munkacella kanbanfeladatait, ha három nem tervezett feladat létezik, a tervező és az üzemirányítási felügyelő számára világosan látható, hogy két nem tervezett feladat végrehajtásra várhat.</span><span class="sxs-lookup"><span data-stu-id="04df4-116">Although automatic planning schedules the kanban jobs for the work cell only when three unplanned jobs exist, it's fully transparent to the planner and the shop floor supervisor that two unplanned jobs might be awaiting execution.</span></span> <span data-ttu-id="04df4-117">A tervező vagy üzemvezető ezután kézzel megtervezheti ezt a két feladatot, vagy ezek mellé további kanbanokat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="04df4-117">The planner or shop floor manager can then take those two jobs into production by manually planning them or creating additional kanbans.</span></span>

## <a name="manual-scheduling"></a><span data-ttu-id="04df4-118">Kézi ütemezés</span><span class="sxs-lookup"><span data-stu-id="04df4-118">Manual scheduling</span></span>
<span data-ttu-id="04df4-119">A Microsoft Dynamics AX 2012 rendszerben bevezettük a kézi ütemezésre szolgáló kanbanütemezési táblát.</span><span class="sxs-lookup"><span data-stu-id="04df4-119">For manual scheduling, Microsoft Dynamics AX 2012 introduced the kanban scheduling board.</span></span> <span data-ttu-id="04df4-120">A kézi ütemezés kombinálható az automatikus ütemezéssel.</span><span class="sxs-lookup"><span data-stu-id="04df4-120">Manual scheduling can be combined with automatic scheduling.</span></span> <span data-ttu-id="04df4-121">A kanbanütemezési tábla segítségével tervezetté vagy nem tervezetté teheti a feladatokat, sorrendbe rakhatja, valamint időszakból időszakba helyezheti azokat.</span><span class="sxs-lookup"><span data-stu-id="04df4-121">The kanban scheduling board lets you plan and unplan jobs, moved them in sequence, or move them from period to period.</span></span> <span data-ttu-id="04df4-122">Azok a feladatok, amelyek **0**-nál nagyobb **Automatikus tervezés** értékű kanbanszabályon alapulnak, kézzel átállíthatók nem tervezetté.</span><span class="sxs-lookup"><span data-stu-id="04df4-122">Jobs that are based on a kanban rule where the **Automatic planning** value is more than **0** can be manually unplanned.</span></span> <span data-ttu-id="04df4-123">Azonban ezek a feladatok újra tervezetté válnak, amint megtörténik a következő automatikus tervezési esemény (tehát amint új kanban jön létre).</span><span class="sxs-lookup"><span data-stu-id="04df4-123">However, these jobs will be replanned when the next automatic planning event occurs (that is, when a new kanban is created).</span></span> <span data-ttu-id="04df4-124">Kézi ütemezés során a következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="04df4-124">The following options are available for manual scheduling:</span></span>

-   <span data-ttu-id="04df4-125">Az **Ütemezés** lehetőség az esedékességi dátumok alapján ütemezi a kiválasztott feladatokat.</span><span class="sxs-lookup"><span data-stu-id="04df4-125">**Schedule** schedules the selected jobs according to their due date.</span></span> <span data-ttu-id="04df4-126">(Az automatikus tervezéshez hasonlóan)</span><span class="sxs-lookup"><span data-stu-id="04df4-126">(This option resembles automatic planning.)</span></span>
-   <span data-ttu-id="04df4-127">Az **Ütemezés megadott dátumtól előre** lehetőség megkísérli a kiválasztott feladatok esedékességi dátum szerinti ütemezését, azonban az eredményt a megadott legkorábbi kezdő dátum alapján leszűkíti.</span><span class="sxs-lookup"><span data-stu-id="04df4-127">**Schedule forward from date** tries to schedule the selected jobs according to their due date but constrains the result by using the specified earliest start date.</span></span>
-   <span data-ttu-id="04df4-128">A **Vissza** lehetőség visszafelé mozgatja a kiválasztott ütemezett feladatokat a sorban, az időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="04df4-128">**Backward** moves the selected scheduled jobs back in the sequence within the period.</span></span>
-   <span data-ttu-id="04df4-129">Az **Előre** lehetőség előrefelé mozgatja a kiválasztott ütemezett feladatokat a sorban, az időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="04df4-129">**Forward** moves the selected scheduled jobs forward in the sequence with the period.</span></span>
-   <span data-ttu-id="04df4-130">Az **Előző időszak** lehetőség áthelyezi a kijelölt ütemezett feladatokat a megelőző időszak elejére vagy végére.</span><span class="sxs-lookup"><span data-stu-id="04df4-130">**Previous period** moves the selected scheduled jobs to the start or end of the previous period.</span></span>
-   <span data-ttu-id="04df4-131">A **Következő időszak** lehetőség áthelyezi a kijelölt ütemezett feladatokat a következő időszak elejére vagy végére.</span><span class="sxs-lookup"><span data-stu-id="04df4-131">**Next period** moves the selected scheduled jobs to the start or end of the next period.</span></span>
-   <span data-ttu-id="04df4-132">A **Terv** &gt; **Feladat állapotának visszaállítása** lehetőséggel visszavonhatja a már ütemezett feladatok ütemezését.</span><span class="sxs-lookup"><span data-stu-id="04df4-132">**Plan** &gt; **Revert job status** lets you unschedule a scheduled job.</span></span>

## <a name="lean-scheduling-groups"></a><span data-ttu-id="04df4-133">Lean ütemezési csoportok</span><span class="sxs-lookup"><span data-stu-id="04df4-133">Lean scheduling groups</span></span>
<span data-ttu-id="04df4-134">Minden egyes szín egy lean ütemezési csoportot jelöl.</span><span class="sxs-lookup"><span data-stu-id="04df4-134">Each color represents a lean scheduling group.</span></span> <span data-ttu-id="04df4-135">A lean ütemezési csoportok kötöttségek nélkül megadhatóak általános csoportokként vagy egyetlen munkacellához tartozó csoportokként.</span><span class="sxs-lookup"><span data-stu-id="04df4-135">Lean scheduling groups can be freely defined as generic groups or as groups that belong to a single work cell.</span></span> <span data-ttu-id="04df4-136">Az ütemezési csoportokhoz tetszőlegesen hozzárendelhetőek cikkek és dimenziók.</span><span class="sxs-lookup"><span data-stu-id="04df4-136">Items and dimensions can be freely assigned to the scheduling groups.</span></span> <span data-ttu-id="04df4-137">Például a Festés cellákban ütemezési csoportok jelölhetik a termék színeit.</span><span class="sxs-lookup"><span data-stu-id="04df4-137">For example, in a Painting cell, a schedule group can represent a color of the product.</span></span> <span data-ttu-id="04df4-138">Egy megadott eszközigényű munka során a cikkek csoportosíthatóak a szükséges szerszámok szerint, illetve egy csomagolási munkacella segítségével csomagolási sablon szerint.</span><span class="sxs-lookup"><span data-stu-id="04df4-138">In work that is driven by specific tooling requirements, items might be grouped by tool requirement, and a packaging work cell might group items by packaging template.</span></span> <span data-ttu-id="04df4-139">A lean ütemezési feladatokhoz nem kötelező, de ajánlott színeket használni.</span><span class="sxs-lookup"><span data-stu-id="04df4-139">The use of colors for lean scheduling groups is optional but recommended.</span></span> <span data-ttu-id="04df4-140">Ez javítja terv állapotának átláthatóságát.</span><span class="sxs-lookup"><span data-stu-id="04df4-140">It improves visibility into the status of the plan.</span></span> <span data-ttu-id="04df4-141">Például egyszerűen megállapítható, hogy milyen színek jelennek meg az egyes napokon, és egy pillanat alatt meg tudja mondani, hogyan optimalizálható ez a munka.</span><span class="sxs-lookup"><span data-stu-id="04df4-141">For example, it's very easy to see which colors are produced on which day, and you can tell at a glance how this work can be optimized.</span></span>

## <a name="work-cell-capacity-and-period-capacity"></a><span data-ttu-id="04df4-142">Munkacella kapacitása és időszak kapacitása</span><span class="sxs-lookup"><span data-stu-id="04df4-142">Work cell capacity and period capacity</span></span>
<span data-ttu-id="04df4-143">Egy lean munkacella kapacitása mindig egyidejű.</span><span class="sxs-lookup"><span data-stu-id="04df4-143">The capacity of a lean work cell is always concurrent capacity.</span></span> <span data-ttu-id="04df4-144">Ez azt jelenti, hogy egy munkacellában több feladat is lehet aktív ugyanabban az időpontban.</span><span class="sxs-lookup"><span data-stu-id="04df4-144">In other words, multiple jobs can be active in a work cell at the same time.</span></span> <span data-ttu-id="04df4-145">A kapacitás nyomon követése kétféleképpen történhet: átfutás és idő alapján.</span><span class="sxs-lookup"><span data-stu-id="04df4-145">The capacity can be tracked in two modes: throughput and hours.</span></span>

### <a name="throughput"></a><span data-ttu-id="04df4-146">Átfutás</span><span class="sxs-lookup"><span data-stu-id="04df4-146">Throughput</span></span>

<span data-ttu-id="04df4-147">A munkacella kapacitását egy referencia időszak (szokásos munkanap, hét, vagy hónap) alatti átlagos átvitt mennyiség definiálja.</span><span class="sxs-lookup"><span data-stu-id="04df4-147">The capacity of a work cell is defined by the average throughput quantity of a reference period (standard workday, week, or month).</span></span> <span data-ttu-id="04df4-148">A napra vagy hétre vonatkoztatott tényleges kapacitást a rendszer a munkacellához rendelt naptárban lévő munkaidő alapján számítja ki.</span><span class="sxs-lookup"><span data-stu-id="04df4-148">The actual capacity per day or week is then calculated based on the working times of the calendar that is assigned to the work cell.</span></span> <span data-ttu-id="04df4-149">Az egyes feladatokhoz tartozó kapacitásokat a munkacellában lévő cikk átviteli arányával korrigált, adott feladathoz tartozó mennyiségek adják meg.</span><span class="sxs-lookup"><span data-stu-id="04df4-149">The capacity that is loaded by job is the quantity of the job, adjusted by the throughput ratio of the item in the work cell.</span></span>

### <a name="hours"></a><span data-ttu-id="04df4-150">Órák</span><span class="sxs-lookup"><span data-stu-id="04df4-150">Hours</span></span>

<span data-ttu-id="04df4-151">A napi vagy heti elérhető kapacitást a munkacellához rendelt naptár definiálja.</span><span class="sxs-lookup"><span data-stu-id="04df4-151">The available capacity by day or week is defined by the calendar that is assigned to the work cell.</span></span> <span data-ttu-id="04df4-152">Az egyes feladatokhoz tartozó kapacitásokat a munkacellában lévő cikk mennyiségével (alapértelmezett tevékenységmennyiség és tényleges feladatmennyiség összevetése) és átviteli arányával korrigált, adott tevékenységhez tartozó ciklusidők adják meg.</span><span class="sxs-lookup"><span data-stu-id="04df4-152">The capacity that is loaded by job is the cycle time of the activity, adjusted by the quantity (default activity quantity versus actual job quantity) and the throughput ratio of the item in the work cell.</span></span>

#### <a name="period-capacity-factbox"></a><span data-ttu-id="04df4-153">Időszak kapacitása adatterület</span><span class="sxs-lookup"><span data-stu-id="04df4-153">Period capacity FactBox</span></span>

<span data-ttu-id="04df4-154">A **Kanbanfeladat ütemezése** listaoldal tartalmaz egy olyan adatterületet, amely a kiválasztott munkacella elérhető és lefoglalt kapacitását mutatja időszakokra vonatkoztatva.</span><span class="sxs-lookup"><span data-stu-id="04df4-154">The **Kanban job scheduling** list page contains a FactBox that shows the available and booked period capacity for the selected work cell.</span></span> <span data-ttu-id="04df4-155">A termelési folyamatmodellben kiválasztott ütemezési időszakoktól függően az időszakok napok vagy hetek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="04df4-155">Depending on the selected schedule periods in the production flow model, the periods show days or weeks.</span></span>

<a name="see-also"></a><span data-ttu-id="04df4-156">Lásd még</span><span class="sxs-lookup"><span data-stu-id="04df4-156">See also</span></span>
--------



