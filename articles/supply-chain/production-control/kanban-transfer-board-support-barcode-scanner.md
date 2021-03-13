---
title: Kanban átviteli tábla támogatás vonalkódolvasókhoz
description: A Kanban átviteli tábla támogatja vezérlő vonalkód leolvasó szkenner bemenetét, így annak segítségével kiválaszthatja, elindíthatja, teljesítheti és kiürítheti a kanban feladatot.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aedfe7ef96d62401b1d0de0f2cd035036c68e51a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007066"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="15d6a-103">Kanban átviteli tábla támogatás vonalkódolvasókhoz</span><span class="sxs-lookup"><span data-stu-id="15d6a-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15d6a-104">A Kanban átviteli tábla támogatja vezérlő vonalkód leolvasó szkenner bemenetét, így annak segítségével kiválaszthatja, elindíthatja, teljesítheti és kiürítheti a kanban feladatot.</span><span class="sxs-lookup"><span data-stu-id="15d6a-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="15d6a-105">Regisztrációs módok</span><span class="sxs-lookup"><span data-stu-id="15d6a-105">Registration modes</span></span>
------------------

<span data-ttu-id="15d6a-106">A **Leolvasó regisztrálása** gyorslapon kiválaszthatja a regisztrációs módot, amely irányítja a műveletet, ha beolvassa a kanbankártya számát vagy manuálisan írja be a számot a Kanbankártya száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="15d6a-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="15d6a-107">Regisztrációs mód beállítása</span><span class="sxs-lookup"><span data-stu-id="15d6a-107">Set registration mode</span></span> | <span data-ttu-id="15d6a-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="15d6a-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="15d6a-109">Kezdő</span><span class="sxs-lookup"><span data-stu-id="15d6a-109">Start</span></span>                 | <span data-ttu-id="15d6a-110">A Kanban átviteli feladat regisztrálása folyamatban lévőként.</span><span class="sxs-lookup"><span data-stu-id="15d6a-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="15d6a-111">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="15d6a-111">Complete</span></span>              | <span data-ttu-id="15d6a-112">A Kanban átviteli feladat regisztrálása befejeződöttként.</span><span class="sxs-lookup"><span data-stu-id="15d6a-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="15d6a-113">Üres</span><span class="sxs-lookup"><span data-stu-id="15d6a-113">Empty</span></span>                 | <span data-ttu-id="15d6a-114">A kanbankártya által üresként hivatkozott anyagkezelési egység regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="15d6a-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="15d6a-115">Kijelölés</span><span class="sxs-lookup"><span data-stu-id="15d6a-115">Select</span></span>                | <span data-ttu-id="15d6a-116">Kanbankártya számának regisztrálása és a hivatkozott feladat automatikus kiválasztása a kanbanfeladatok listájában.</span><span class="sxs-lookup"><span data-stu-id="15d6a-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="15d6a-117">Regisztrációs mód kiválasztása</span><span class="sxs-lookup"><span data-stu-id="15d6a-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="15d6a-118">Amikor vonalkódolvasó segítségével választ ki egy feladatot, a kanban tábla megjelenítési módja megváltozik.</span><span class="sxs-lookup"><span data-stu-id="15d6a-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="15d6a-119">Ebben a módban a következő feltételek érvényesek:</span><span class="sxs-lookup"><span data-stu-id="15d6a-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="15d6a-120">Csak a beolvasott kanbanfeladat jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="15d6a-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="15d6a-121">A kiválasztott feladat részletei megjelennek a **Részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="15d6a-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="15d6a-122">Az **Üzenetek** gyorslap csak a kijelölt feladathoz jelenít meg az üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="15d6a-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="15d6a-123">A feladat állapota a rendelkezésre álló funkciók használatával módosítható a Műveleti ablak modulban.</span><span class="sxs-lookup"><span data-stu-id="15d6a-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="15d6a-124">Ezalatt a Kanban átviteli tábla továbbra is a csak egyetlen feladatot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="15d6a-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="15d6a-125">A feladatok a listáján szereplő adatokat manuálisan frissítheti a **Frissítés** (Shift + F5) lehetőségre kattintva műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="15d6a-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="15d6a-126">Az adatok frissítése után a feladatszűrő teljes eredményei jelennek meg ismét.</span><span class="sxs-lookup"><span data-stu-id="15d6a-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="15d6a-127">Feladat állapota, és a lehetséges műveletek</span><span class="sxs-lookup"><span data-stu-id="15d6a-127">Job status and possible actions</span></span>
<span data-ttu-id="15d6a-128">Az eseménykanbanoknál a kijelölt feladatok és a rögzített feladatok állapota határozza meg, hogy lehet-e tovább feldolgozni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="15d6a-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="15d6a-129">Az alábbi táblázat a következő állapotok és feladatok adatait jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="15d6a-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="15d6a-130">Az állapotok, amelyek a feladatokhoz vagy a feladatok által hivatkozott anyagkezelési egységekhez állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="15d6a-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="15d6a-131">Minden feladat, amely elvégezhető a munkához.</span><span class="sxs-lookup"><span data-stu-id="15d6a-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d6a-132">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="15d6a-132">Job type</span></span></th>
<th><span data-ttu-id="15d6a-133">Feladat állapota vagy az anyagkezelési egység állapota</span><span class="sxs-lookup"><span data-stu-id="15d6a-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="15d6a-134">Kitárolási lista frissítése</span><span class="sxs-lookup"><span data-stu-id="15d6a-134">Update picking list</span></span></th>
<th><span data-ttu-id="15d6a-135">Kezdő</span><span class="sxs-lookup"><span data-stu-id="15d6a-135">Start</span></span></th>
<th><span data-ttu-id="15d6a-136">Regisztráció frissítése</span><span class="sxs-lookup"><span data-stu-id="15d6a-136">Update registration</span></span></th>
<th><span data-ttu-id="15d6a-137">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="15d6a-137">Complete</span></span></th>
<th><span data-ttu-id="15d6a-138">Üres</span><span class="sxs-lookup"><span data-stu-id="15d6a-138">Empty</span></span></th>
<th><span data-ttu-id="15d6a-139">Eseménykanbanok létrehozása</span><span class="sxs-lookup"><span data-stu-id="15d6a-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="15d6a-140">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="15d6a-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="15d6a-141">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="15d6a-141">Not planned</span></span></li>
<li><span data-ttu-id="15d6a-142">Nincsenek rögzített feladatok vagy a rögzített feladatok befejeződtek.</span><span class="sxs-lookup"><span data-stu-id="15d6a-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="15d6a-143">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-143">Yes</span></span></td>
<td><span data-ttu-id="15d6a-144">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-144">Yes</span></span></td>
<td><span data-ttu-id="15d6a-145">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-145">Yes</span></span></td>
<td><span data-ttu-id="15d6a-146">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-146">Yes</span></span></td>
<td><span data-ttu-id="15d6a-147">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-147">No</span></span></td>
<td><span data-ttu-id="15d6a-148">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="15d6a-149">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="15d6a-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="15d6a-150">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="15d6a-150">Not planned</span></span></li>
<li><span data-ttu-id="15d6a-151">A rögzített feladat nincs Befejezve.</span><span class="sxs-lookup"><span data-stu-id="15d6a-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="15d6a-152">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-152">Yes</span></span></td>
<td><span data-ttu-id="15d6a-153">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-153">No</span></span></td>
<td><span data-ttu-id="15d6a-154">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-154">Yes</span></span></td>
<td><span data-ttu-id="15d6a-155">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-155">No</span></span></td>
<td><span data-ttu-id="15d6a-156">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-156">No</span></span></td>
<td><span data-ttu-id="15d6a-157">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="15d6a-158">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="15d6a-158">Transfer</span></span></td>
<td><span data-ttu-id="15d6a-159">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="15d6a-159">In progress</span></span></td>
<td><span data-ttu-id="15d6a-160">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-160">Yes</span></span></td>
<td><span data-ttu-id="15d6a-161">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-161">No</span></span></td>
<td><span data-ttu-id="15d6a-162">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-162">Yes</span></span></td>
<td><span data-ttu-id="15d6a-163">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-163">Yes</span></span></td>
<td><span data-ttu-id="15d6a-164">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-164">No</span></span></td>
<td><span data-ttu-id="15d6a-165">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="15d6a-166">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="15d6a-166">Transfer</span></span></td>
<td><span data-ttu-id="15d6a-167">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="15d6a-167">Completed</span></span></td>
<td><span data-ttu-id="15d6a-168">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-168">No</span></span></td>
<td><span data-ttu-id="15d6a-169">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-169">No</span></span></td>
<td><span data-ttu-id="15d6a-170">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-170">No</span></span></td>
<td><span data-ttu-id="15d6a-171">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-171">No</span></span></td>
<td><span data-ttu-id="15d6a-172">Igen</span><span class="sxs-lookup"><span data-stu-id="15d6a-172">Yes</span></span></td>
<td><span data-ttu-id="15d6a-173">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="15d6a-174">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="15d6a-174">Transfer or process</span></span></td>
<td><span data-ttu-id="15d6a-175">Üres</span><span class="sxs-lookup"><span data-stu-id="15d6a-175">Empty</span></span></td>
<td><span data-ttu-id="15d6a-176">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-176">No</span></span></td>
<td><span data-ttu-id="15d6a-177">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-177">No</span></span></td>
<td><span data-ttu-id="15d6a-178">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-178">No</span></span></td>
<td><span data-ttu-id="15d6a-179">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-179">No</span></span></td>
<td><span data-ttu-id="15d6a-180">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-180">No</span></span></td>
<td><span data-ttu-id="15d6a-181">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="15d6a-182">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="15d6a-182">Transfer or process</span></span></td>
<td><span data-ttu-id="15d6a-183">A kanbankártya nem található</span><span class="sxs-lookup"><span data-stu-id="15d6a-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="15d6a-184">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-184">No</span></span></td>
<td><span data-ttu-id="15d6a-185">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-185">No</span></span></td>
<td><span data-ttu-id="15d6a-186">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-186">No</span></span></td>
<td><span data-ttu-id="15d6a-187">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-187">No</span></span></td>
<td><span data-ttu-id="15d6a-188">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-188">No</span></span></td>
<td><span data-ttu-id="15d6a-189">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="15d6a-190">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="15d6a-190">Transfer or process</span></span></td>
<td><span data-ttu-id="15d6a-191">A kanbankártya megtalálható, de nincs hozzárendelve kanbanhoz</span><span class="sxs-lookup"><span data-stu-id="15d6a-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="15d6a-192">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-192">No</span></span></td>
<td><span data-ttu-id="15d6a-193">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-193">No</span></span></td>
<td><span data-ttu-id="15d6a-194">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-194">No</span></span></td>
<td><span data-ttu-id="15d6a-195">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-195">No</span></span></td>
<td><span data-ttu-id="15d6a-196">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-196">No</span></span></td>
<td><span data-ttu-id="15d6a-197">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="15d6a-198">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="15d6a-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="15d6a-199">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="15d6a-199">Not planned</span></span></li>
<li><span data-ttu-id="15d6a-200">Előkészítve</span><span class="sxs-lookup"><span data-stu-id="15d6a-200">Prepared</span></span></li>
<li><span data-ttu-id="15d6a-201">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="15d6a-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="15d6a-202">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-202">No</span></span></td>
<td><span data-ttu-id="15d6a-203">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-203">No</span></span></td>
<td><span data-ttu-id="15d6a-204">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-204">No</span></span></td>
<td><span data-ttu-id="15d6a-205">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-205">No</span></span></td>
<td><span data-ttu-id="15d6a-206">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-206">No</span></span></td>
<td><span data-ttu-id="15d6a-207">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="15d6a-208">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="15d6a-208">Process</span></span></td>
<td><span data-ttu-id="15d6a-209">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="15d6a-209">Completed</span></span></td>
<td><span data-ttu-id="15d6a-210">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-210">No</span></span></td>
<td><span data-ttu-id="15d6a-211">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-211">No</span></span></td>
<td><span data-ttu-id="15d6a-212">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-212">No</span></span></td>
<td><span data-ttu-id="15d6a-213">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-213">No</span></span></td>
<td><span data-ttu-id="15d6a-214">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-214">No</span></span></td>
<td><span data-ttu-id="15d6a-215">Szám</span><span class="sxs-lookup"><span data-stu-id="15d6a-215">No</span></span></td>
</tr>
</tbody>
</table>





