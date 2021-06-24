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
ms.openlocfilehash: c48c4737c260004ea44109cfb2a0478a3e8653cc
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6190064"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="3605c-103">Kanban átviteli tábla támogatás vonalkódolvasókhoz</span><span class="sxs-lookup"><span data-stu-id="3605c-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3605c-104">A Kanban átviteli tábla támogatja vezérlő vonalkód leolvasó szkenner bemenetét, így annak segítségével kiválaszthatja, elindíthatja, teljesítheti és kiürítheti a kanban feladatot.</span><span class="sxs-lookup"><span data-stu-id="3605c-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

## <a name="registration-modes"></a><span data-ttu-id="3605c-105">Regisztrációs módok</span><span class="sxs-lookup"><span data-stu-id="3605c-105">Registration modes</span></span>

<span data-ttu-id="3605c-106">A **Leolvasó regisztrálása** gyorslapon kiválaszthatja a regisztrációs módot, amely irányítja a műveletet, ha beolvassa a kanbankártya számát vagy manuálisan írja be a számot a Kanbankártya száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3605c-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="3605c-107">Regisztrációs mód beállítása</span><span class="sxs-lookup"><span data-stu-id="3605c-107">Set registration mode</span></span> | <span data-ttu-id="3605c-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="3605c-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3605c-109">Kezdő</span><span class="sxs-lookup"><span data-stu-id="3605c-109">Start</span></span>                 | <span data-ttu-id="3605c-110">A Kanban átviteli feladat regisztrálása folyamatban lévőként.</span><span class="sxs-lookup"><span data-stu-id="3605c-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="3605c-111">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="3605c-111">Complete</span></span>              | <span data-ttu-id="3605c-112">A Kanban átviteli feladat regisztrálása befejeződöttként.</span><span class="sxs-lookup"><span data-stu-id="3605c-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="3605c-113">Üres</span><span class="sxs-lookup"><span data-stu-id="3605c-113">Empty</span></span>                 | <span data-ttu-id="3605c-114">A kanbankártya által üresként hivatkozott anyagkezelési egység regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="3605c-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="3605c-115">Kijelölés</span><span class="sxs-lookup"><span data-stu-id="3605c-115">Select</span></span>                | <span data-ttu-id="3605c-116">Kanbankártya számának regisztrálása és a hivatkozott feladat automatikus kiválasztása a kanbanfeladatok listájában.</span><span class="sxs-lookup"><span data-stu-id="3605c-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
## <a name="registration-mode-select"></a><span data-ttu-id="3605c-117">Regisztrációs mód kiválasztása</span><span class="sxs-lookup"><span data-stu-id="3605c-117">Registration mode Select</span></span>

<span data-ttu-id="3605c-118">Amikor vonalkódolvasó segítségével választ ki egy feladatot, a kanban tábla megjelenítési módja megváltozik.</span><span class="sxs-lookup"><span data-stu-id="3605c-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="3605c-119">Ebben a módban a következő feltételek érvényesek:</span><span class="sxs-lookup"><span data-stu-id="3605c-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="3605c-120">Csak a beolvasott kanbanfeladat jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="3605c-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="3605c-121">A kiválasztott feladat részletei megjelennek a **Részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="3605c-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="3605c-122">Az **Üzenetek** gyorslap csak a kijelölt feladathoz jelenít meg az üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="3605c-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="3605c-123">A feladat állapota a rendelkezésre álló funkciók használatával módosítható a Műveleti ablak modulban.</span><span class="sxs-lookup"><span data-stu-id="3605c-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="3605c-124">Ezalatt a Kanban átviteli tábla továbbra is a csak egyetlen feladatot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="3605c-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="3605c-125">A feladatok a listáján szereplő adatokat manuálisan frissítheti a **Frissítés** (Shift + F5) lehetőségre kattintva műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="3605c-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="3605c-126">Az adatok frissítése után a feladatszűrő teljes eredményei jelennek meg ismét.</span><span class="sxs-lookup"><span data-stu-id="3605c-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="3605c-127">Feladat állapota, és a lehetséges műveletek</span><span class="sxs-lookup"><span data-stu-id="3605c-127">Job status and possible actions</span></span>
<span data-ttu-id="3605c-128">Az eseménykanbanoknál a kijelölt feladatok és a rögzített feladatok állapota határozza meg, hogy lehet-e tovább feldolgozni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="3605c-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="3605c-129">Az alábbi táblázat a következő állapotok és feladatok adatait jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="3605c-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="3605c-130">Az állapotok, amelyek a feladatokhoz vagy a feladatok által hivatkozott anyagkezelési egységekhez állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="3605c-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="3605c-131">Minden feladat, amely elvégezhető a munkához.</span><span class="sxs-lookup"><span data-stu-id="3605c-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="3605c-132">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="3605c-132">Job type</span></span></th>
<th><span data-ttu-id="3605c-133">Feladat állapota vagy az anyagkezelési egység állapota</span><span class="sxs-lookup"><span data-stu-id="3605c-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="3605c-134">Kitárolási lista frissítése</span><span class="sxs-lookup"><span data-stu-id="3605c-134">Update picking list</span></span></th>
<th><span data-ttu-id="3605c-135">Kezdő</span><span class="sxs-lookup"><span data-stu-id="3605c-135">Start</span></span></th>
<th><span data-ttu-id="3605c-136">Regisztráció frissítése</span><span class="sxs-lookup"><span data-stu-id="3605c-136">Update registration</span></span></th>
<th><span data-ttu-id="3605c-137">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="3605c-137">Complete</span></span></th>
<th><span data-ttu-id="3605c-138">Üres</span><span class="sxs-lookup"><span data-stu-id="3605c-138">Empty</span></span></th>
<th><span data-ttu-id="3605c-139">Eseménykanbanok létrehozása</span><span class="sxs-lookup"><span data-stu-id="3605c-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3605c-140">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="3605c-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="3605c-141">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="3605c-141">Not planned</span></span></li>
<li><span data-ttu-id="3605c-142">Nincsenek rögzített feladatok vagy a rögzített feladatok befejeződtek.</span><span class="sxs-lookup"><span data-stu-id="3605c-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="3605c-143">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-143">Yes</span></span></td>
<td><span data-ttu-id="3605c-144">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-144">Yes</span></span></td>
<td><span data-ttu-id="3605c-145">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-145">Yes</span></span></td>
<td><span data-ttu-id="3605c-146">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-146">Yes</span></span></td>
<td><span data-ttu-id="3605c-147">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-147">No</span></span></td>
<td><span data-ttu-id="3605c-148">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3605c-149">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="3605c-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="3605c-150">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="3605c-150">Not planned</span></span></li>
<li><span data-ttu-id="3605c-151">A rögzített feladat nincs Befejezve.</span><span class="sxs-lookup"><span data-stu-id="3605c-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="3605c-152">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-152">Yes</span></span></td>
<td><span data-ttu-id="3605c-153">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-153">No</span></span></td>
<td><span data-ttu-id="3605c-154">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-154">Yes</span></span></td>
<td><span data-ttu-id="3605c-155">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-155">No</span></span></td>
<td><span data-ttu-id="3605c-156">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-156">No</span></span></td>
<td><span data-ttu-id="3605c-157">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3605c-158">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="3605c-158">Transfer</span></span></td>
<td><span data-ttu-id="3605c-159">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="3605c-159">In progress</span></span></td>
<td><span data-ttu-id="3605c-160">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-160">Yes</span></span></td>
<td><span data-ttu-id="3605c-161">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-161">No</span></span></td>
<td><span data-ttu-id="3605c-162">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-162">Yes</span></span></td>
<td><span data-ttu-id="3605c-163">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-163">Yes</span></span></td>
<td><span data-ttu-id="3605c-164">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-164">No</span></span></td>
<td><span data-ttu-id="3605c-165">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3605c-166">Áthelyezés</span><span class="sxs-lookup"><span data-stu-id="3605c-166">Transfer</span></span></td>
<td><span data-ttu-id="3605c-167">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="3605c-167">Completed</span></span></td>
<td><span data-ttu-id="3605c-168">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-168">No</span></span></td>
<td><span data-ttu-id="3605c-169">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-169">No</span></span></td>
<td><span data-ttu-id="3605c-170">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-170">No</span></span></td>
<td><span data-ttu-id="3605c-171">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-171">No</span></span></td>
<td><span data-ttu-id="3605c-172">Igen</span><span class="sxs-lookup"><span data-stu-id="3605c-172">Yes</span></span></td>
<td><span data-ttu-id="3605c-173">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3605c-174">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="3605c-174">Transfer or process</span></span></td>
<td><span data-ttu-id="3605c-175">Üres</span><span class="sxs-lookup"><span data-stu-id="3605c-175">Empty</span></span></td>
<td><span data-ttu-id="3605c-176">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-176">No</span></span></td>
<td><span data-ttu-id="3605c-177">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-177">No</span></span></td>
<td><span data-ttu-id="3605c-178">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-178">No</span></span></td>
<td><span data-ttu-id="3605c-179">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-179">No</span></span></td>
<td><span data-ttu-id="3605c-180">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-180">No</span></span></td>
<td><span data-ttu-id="3605c-181">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3605c-182">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="3605c-182">Transfer or process</span></span></td>
<td><span data-ttu-id="3605c-183">A kanbankártya nem található</span><span class="sxs-lookup"><span data-stu-id="3605c-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="3605c-184">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-184">No</span></span></td>
<td><span data-ttu-id="3605c-185">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-185">No</span></span></td>
<td><span data-ttu-id="3605c-186">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-186">No</span></span></td>
<td><span data-ttu-id="3605c-187">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-187">No</span></span></td>
<td><span data-ttu-id="3605c-188">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-188">No</span></span></td>
<td><span data-ttu-id="3605c-189">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3605c-190">Átvitel vagy folyamat</span><span class="sxs-lookup"><span data-stu-id="3605c-190">Transfer or process</span></span></td>
<td><span data-ttu-id="3605c-191">A kanbankártya megtalálható, de nincs hozzárendelve kanbanhoz</span><span class="sxs-lookup"><span data-stu-id="3605c-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="3605c-192">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-192">No</span></span></td>
<td><span data-ttu-id="3605c-193">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-193">No</span></span></td>
<td><span data-ttu-id="3605c-194">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-194">No</span></span></td>
<td><span data-ttu-id="3605c-195">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-195">No</span></span></td>
<td><span data-ttu-id="3605c-196">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-196">No</span></span></td>
<td><span data-ttu-id="3605c-197">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3605c-198">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="3605c-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="3605c-199">Nem tervezett</span><span class="sxs-lookup"><span data-stu-id="3605c-199">Not planned</span></span></li>
<li><span data-ttu-id="3605c-200">Előkészítve</span><span class="sxs-lookup"><span data-stu-id="3605c-200">Prepared</span></span></li>
<li><span data-ttu-id="3605c-201">Folyamatban</span><span class="sxs-lookup"><span data-stu-id="3605c-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="3605c-202">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-202">No</span></span></td>
<td><span data-ttu-id="3605c-203">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-203">No</span></span></td>
<td><span data-ttu-id="3605c-204">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-204">No</span></span></td>
<td><span data-ttu-id="3605c-205">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-205">No</span></span></td>
<td><span data-ttu-id="3605c-206">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-206">No</span></span></td>
<td><span data-ttu-id="3605c-207">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3605c-208">Feldolgozás</span><span class="sxs-lookup"><span data-stu-id="3605c-208">Process</span></span></td>
<td><span data-ttu-id="3605c-209">Befejeződött</span><span class="sxs-lookup"><span data-stu-id="3605c-209">Completed</span></span></td>
<td><span data-ttu-id="3605c-210">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-210">No</span></span></td>
<td><span data-ttu-id="3605c-211">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-211">No</span></span></td>
<td><span data-ttu-id="3605c-212">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-212">No</span></span></td>
<td><span data-ttu-id="3605c-213">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-213">No</span></span></td>
<td><span data-ttu-id="3605c-214">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-214">No</span></span></td>
<td><span data-ttu-id="3605c-215">Szám</span><span class="sxs-lookup"><span data-stu-id="3605c-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]