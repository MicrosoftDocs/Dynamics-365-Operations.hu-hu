---
title: Kanban átviteli tábla támogatás vonalkódolvasókhoz
description: A Kanban átviteli tábla támogatja vezérlő vonalkód leolvasó szkenner bemenetét, így annak segítségével kiválaszthatja, elindíthatja, teljesítheti és kiürítheti a kanban feladatot.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 2a7073fb5d77e2d11569e86b92433864371f0e1d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825867"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="074c8-103">Kanban átviteli tábla támogatás vonalkódolvasókhoz</span><span class="sxs-lookup"><span data-stu-id="074c8-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="074c8-104">A Kanban átviteli tábla támogatja vezérlő vonalkód leolvasó szkenner bemenetét, így annak segítségével kiválaszthatja, elindíthatja, teljesítheti és kiürítheti a kanban feladatot.</span><span class="sxs-lookup"><span data-stu-id="074c8-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="074c8-105">Regisztrációs módok</span><span class="sxs-lookup"><span data-stu-id="074c8-105">Registration modes</span></span>
------------------

<span data-ttu-id="074c8-106">A **Leolvasó regisztrálása** gyorslapon kiválaszthatja a regisztrációs módot, amely irányítja a műveletet, ha beolvassa a kanbankártya számát vagy manuálisan írja be a számot a Kanbankártya száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="074c8-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="074c8-107">Regisztrációs mód beállítása</span><span class="sxs-lookup"><span data-stu-id="074c8-107">Set registration mode</span></span> | <span data-ttu-id="074c8-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="074c8-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="074c8-109">Kezdő</span><span class="sxs-lookup"><span data-stu-id="074c8-109">Start</span></span>                 | <span data-ttu-id="074c8-110">A Kanban átviteli feladat regisztrálása folyamatban lévőként.</span><span class="sxs-lookup"><span data-stu-id="074c8-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="074c8-111">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="074c8-111">Complete</span></span>              | <span data-ttu-id="074c8-112">A Kanban átviteli feladat regisztrálása befejeződöttként.</span><span class="sxs-lookup"><span data-stu-id="074c8-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="074c8-113">Üres</span><span class="sxs-lookup"><span data-stu-id="074c8-113">Empty</span></span>                 | <span data-ttu-id="074c8-114">A kanbankártya által üresként hivatkozott anyagkezelési egység regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="074c8-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="074c8-115">Kijelölés</span><span class="sxs-lookup"><span data-stu-id="074c8-115">Select</span></span>                | <span data-ttu-id="074c8-116">Kanbankártya számának regisztrálása és a hivatkozott feladat automatikus kiválasztása a kanbanfeladatok listájában.</span><span class="sxs-lookup"><span data-stu-id="074c8-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="074c8-117">Regisztrációs mód kiválasztása</span><span class="sxs-lookup"><span data-stu-id="074c8-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="074c8-118">Amikor vonalkódolvasó segítségével választ ki egy feladatot, a kanban tábla megjelenítési módja megváltozik.</span><span class="sxs-lookup"><span data-stu-id="074c8-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="074c8-119">Ebben a módban a következő feltételek érvényesek:</span><span class="sxs-lookup"><span data-stu-id="074c8-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="074c8-120">Csak a beolvasott kanbanfeladat jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="074c8-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="074c8-121">A kiválasztott feladat részletei megjelennek a **Részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="074c8-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="074c8-122">Az **Üzenetek** gyorslap csak a kijelölt feladathoz jelenít meg az üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="074c8-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="074c8-123">A feladat állapota a rendelkezésre álló funkciók használatával módosítható a Műveleti ablak modulban.</span><span class="sxs-lookup"><span data-stu-id="074c8-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="074c8-124">Ezalatt a Kanban átviteli tábla továbbra is a csak egyetlen feladatot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="074c8-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="074c8-125">A feladatok a listáján szereplő adatokat manuálisan frissítheti a **Frissítés** (Shift + F5) lehetőségre kattintva műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="074c8-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="074c8-126">Az adatok frissítése után a feladatszűrő teljes eredményei jelennek meg ismét.</span><span class="sxs-lookup"><span data-stu-id="074c8-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="074c8-127">Feladat állapota, és a lehetséges műveletek</span><span class="sxs-lookup"><span data-stu-id="074c8-127">Job status and possible actions</span></span>
<span data-ttu-id="074c8-128">Az eseménykanbanoknál a kijelölt feladatok és a rögzített feladatok állapota határozza meg, hogy lehet-e tovább feldolgozni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="074c8-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="074c8-129">Az alábbi táblázat a következő állapotok és feladatok adatait jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="074c8-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="074c8-130">Az állapotok, amelyek a feladatokhoz vagy a feladatok által hivatkozott anyagkezelési egységekhez állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="074c8-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="074c8-131">Minden feladat, amely elvégezhető a munkához.</span><span class="sxs-lookup"><span data-stu-id="074c8-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="074c8-132">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="074c8-132">Job type</span></span></th>
<th><span data-ttu-id="074c8-133">Feladat állapota vagy az anyagkezelési egység állapota</span><span class="sxs-lookup"><span data-stu-id="074c8-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="074c8-134">Kitárolási lista frissítése</span><span class="sxs-lookup"><span data-stu-id="074c8-134">Update picking list</span></span></th>
<th><span data-ttu-id="074c8-135">Kezdő</span><span class="sxs-lookup"><span data-stu-id="074c8-135">Start</span></span></th>
<th><span data-ttu-id="074c8-136">Regisztráció frissítése</span><span class="sxs-lookup"><span data-stu-id="074c8-136">Update registration</span></span></th>
<th><span data-ttu-id="074c8-137">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="074c8-137">Complete</span></span></th>
<th><span data-ttu-id="074c8-138">Üres</span><span class="sxs-lookup"><span data-stu-id="074c8-138">Empty</span></span></th>
<th><span data-ttu-id="074c8-139">Eseménykanbanok létrehozása</span><span class="sxs-lookup"><span data-stu-id="074c8-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="074c8-140">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="074c8-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="074c8-141">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="074c8-141">Not planned</span></span></li>
<li><span data-ttu-id="074c8-142">Nincsenek rögzített feladatok vagy a rögzített feladatok befejeződtek.</span><span class="sxs-lookup"><span data-stu-id="074c8-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="074c8-143">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-143">Yes</span></span></td>
<td><span data-ttu-id="074c8-144">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-144">Yes</span></span></td>
<td><span data-ttu-id="074c8-145">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-145">Yes</span></span></td>
<td><span data-ttu-id="074c8-146">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-146">Yes</span></span></td>
<td><span data-ttu-id="074c8-147">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-147">No</span></span></td>
<td><span data-ttu-id="074c8-148">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="074c8-149">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="074c8-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="074c8-150">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="074c8-150">Not planned</span></span></li>
<li><span data-ttu-id="074c8-151">A rögzített feladat nincs Befejezve.</span><span class="sxs-lookup"><span data-stu-id="074c8-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="074c8-152">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-152">Yes</span></span></td>
<td><span data-ttu-id="074c8-153">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-153">No</span></span></td>
<td><span data-ttu-id="074c8-154">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-154">Yes</span></span></td>
<td><span data-ttu-id="074c8-155">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-155">No</span></span></td>
<td><span data-ttu-id="074c8-156">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-156">No</span></span></td>
<td><span data-ttu-id="074c8-157">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="074c8-158">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="074c8-158">Transfer</span></span></td>
<td><span data-ttu-id="074c8-159">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="074c8-159">In progress</span></span></td>
<td><span data-ttu-id="074c8-160">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-160">Yes</span></span></td>
<td><span data-ttu-id="074c8-161">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-161">No</span></span></td>
<td><span data-ttu-id="074c8-162">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-162">Yes</span></span></td>
<td><span data-ttu-id="074c8-163">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-163">Yes</span></span></td>
<td><span data-ttu-id="074c8-164">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-164">No</span></span></td>
<td><span data-ttu-id="074c8-165">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="074c8-166">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="074c8-166">Transfer</span></span></td>
<td><span data-ttu-id="074c8-167">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="074c8-167">Completed</span></span></td>
<td><span data-ttu-id="074c8-168">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-168">No</span></span></td>
<td><span data-ttu-id="074c8-169">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-169">No</span></span></td>
<td><span data-ttu-id="074c8-170">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-170">No</span></span></td>
<td><span data-ttu-id="074c8-171">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-171">No</span></span></td>
<td><span data-ttu-id="074c8-172">Igen</span><span class="sxs-lookup"><span data-stu-id="074c8-172">Yes</span></span></td>
<td><span data-ttu-id="074c8-173">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="074c8-174">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="074c8-174">Transfer or process</span></span></td>
<td><span data-ttu-id="074c8-175">Üres</span><span class="sxs-lookup"><span data-stu-id="074c8-175">Empty</span></span></td>
<td><span data-ttu-id="074c8-176">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-176">No</span></span></td>
<td><span data-ttu-id="074c8-177">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-177">No</span></span></td>
<td><span data-ttu-id="074c8-178">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-178">No</span></span></td>
<td><span data-ttu-id="074c8-179">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-179">No</span></span></td>
<td><span data-ttu-id="074c8-180">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-180">No</span></span></td>
<td><span data-ttu-id="074c8-181">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="074c8-182">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="074c8-182">Transfer or process</span></span></td>
<td><span data-ttu-id="074c8-183">A kanbankártya nem található</span><span class="sxs-lookup"><span data-stu-id="074c8-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="074c8-184">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-184">No</span></span></td>
<td><span data-ttu-id="074c8-185">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-185">No</span></span></td>
<td><span data-ttu-id="074c8-186">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-186">No</span></span></td>
<td><span data-ttu-id="074c8-187">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-187">No</span></span></td>
<td><span data-ttu-id="074c8-188">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-188">No</span></span></td>
<td><span data-ttu-id="074c8-189">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="074c8-190">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="074c8-190">Transfer or process</span></span></td>
<td><span data-ttu-id="074c8-191">A kanbankártya megtalálható, de nincs hozzárendelve kanbanhoz</span><span class="sxs-lookup"><span data-stu-id="074c8-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="074c8-192">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-192">No</span></span></td>
<td><span data-ttu-id="074c8-193">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-193">No</span></span></td>
<td><span data-ttu-id="074c8-194">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-194">No</span></span></td>
<td><span data-ttu-id="074c8-195">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-195">No</span></span></td>
<td><span data-ttu-id="074c8-196">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-196">No</span></span></td>
<td><span data-ttu-id="074c8-197">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="074c8-198">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="074c8-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="074c8-199">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="074c8-199">Not planned</span></span></li>
<li><span data-ttu-id="074c8-200">Előkészítve</span><span class="sxs-lookup"><span data-stu-id="074c8-200">Prepared</span></span></li>
<li><span data-ttu-id="074c8-201">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="074c8-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="074c8-202">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-202">No</span></span></td>
<td><span data-ttu-id="074c8-203">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-203">No</span></span></td>
<td><span data-ttu-id="074c8-204">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-204">No</span></span></td>
<td><span data-ttu-id="074c8-205">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-205">No</span></span></td>
<td><span data-ttu-id="074c8-206">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-206">No</span></span></td>
<td><span data-ttu-id="074c8-207">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="074c8-208">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="074c8-208">Process</span></span></td>
<td><span data-ttu-id="074c8-209">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="074c8-209">Completed</span></span></td>
<td><span data-ttu-id="074c8-210">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-210">No</span></span></td>
<td><span data-ttu-id="074c8-211">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-211">No</span></span></td>
<td><span data-ttu-id="074c8-212">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-212">No</span></span></td>
<td><span data-ttu-id="074c8-213">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-213">No</span></span></td>
<td><span data-ttu-id="074c8-214">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-214">No</span></span></td>
<td><span data-ttu-id="074c8-215">Szám</span><span class="sxs-lookup"><span data-stu-id="074c8-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]