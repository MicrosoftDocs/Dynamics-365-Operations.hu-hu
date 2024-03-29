---
title: Kanbanátviteli tábla támogatása vonalkódolvasókhoz
description: A Kanbanátviteli tábla támogatja a widget vonalkódolvasóról történő beolvasást a kanban munkák kiválasztásához, indításához, befejezéséhez és kiürítéséhez.
author: johanhoffmann
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
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566811"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>Kanbanátviteli tábla támogatása vonalkódolvasókhoz

[!include [banner](../includes/banner.md)]

A Kanbanátviteli tábla támogatja a widget vonalkódolvasóról történő beolvasást a kanban munkák kiválasztásához, indításához, befejezéséhez és kiürítéséhez.

## <a name="registration-modes"></a>Regisztrációs módok

A **Leolvasó regisztrálása** gyorslapon kiválaszthatja a regisztrációs módot, amely irányítja a műveletet, ha beolvassa a kanbankártya számát vagy manuálisan írja be a számot a Kanbankártya száma mezőbe.

| Regisztrációs mód beállítása | Leírás                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Kezdő                 | A Kanban átviteli feladat regisztrálása folyamatban lévőként.                                                 |
| Befejeződött              | A Kanban átviteli feladat regisztrálása befejeződöttként.                                                   |
| Üres                 | A kanbankártya által üresként hivatkozott anyagkezelési egység regisztrálása.              |
| Kijelölés                | Kanbankártya számának regisztrálása és a hivatkozott feladat automatikus kiválasztása a kanbanfeladatok listájában. |

 
## <a name="registration-mode-select"></a>Regisztrációs mód kiválasztása

Amikor vonalkódolvasó segítségével választ ki egy feladatot, a kanban tábla megjelenítési módja megváltozik. Ebben a módban a következő feltételek érvényesek:

-   Csak a beolvasott kanbanfeladat jelenik meg.
-   A kiválasztott feladat részletei megjelennek a **Részletek** gyorslapon.
-   Az **Üzenetek** gyorslap csak a kijelölt feladathoz jelenít meg az üzeneteket.
-   A feladat állapota a rendelkezésre álló funkciók használatával módosítható a Műveleti ablak modulban. Ezalatt a Kanban átviteli tábla továbbra is a csak egyetlen feladatot jelenít meg.
-   A feladatok a listáján szereplő adatokat manuálisan frissítheti a **Frissítés** (Shift + F5) lehetőségre kattintva műveleti panelen. Az adatok frissítése után a feladatszűrő teljes eredményei jelennek meg ismét.

## <a name="job-status-and-possible-actions"></a>Feladat állapota, és a lehetséges műveletek
Az eseménykanbanoknál a kijelölt feladatok és a rögzített feladatok állapota határozza meg, hogy lehet-e tovább feldolgozni a feladatot. Az alábbi táblázat a következő állapotok és feladatok adatait jeleníti meg:
-   Az állapotok, amelyek a feladatokhoz vagy a feladatok által hivatkozott anyagkezelési egységekhez állnak rendelkezésre.
-   Minden feladat, amely elvégezhető a munkához.

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
<th>Feladattípus</th>
<th>Feladat állapota vagy az anyagkezelési egység állapota</th>
<th>Kitárolási lista frissítése</th>
<th>Kezdő</th>
<th>Regisztráció frissítése</th>
<th>Befejeződött</th>
<th>Üres</th>
<th>Eseménykanbanok létrehozása</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Áthelyezés</td>
<td><ul>
<li>Nem tervezett</li>
<li>Nincsenek rögzített feladatok vagy a rögzített feladatok befejeződtek.</li>
</ul></td>
<td>Igen</td>
<td>Igen</td>
<td>Igen</td>
<td>Igen</td>
<td>Nem</td>
<td>Igen</td>
</tr>
<tr class="even">
<td>Áthelyezés</td>
<td><ul>
<li>Nem tervezett</li>
<li>A rögzített feladat nincs Befejezve.</li>
</ul></td>
<td>Igen</td>
<td>Nem</td>
<td>Igen</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="odd">
<td>Áthelyezés</td>
<td>Folyamatban</td>
<td>Igen</td>
<td>Nem</td>
<td>Igen</td>
<td>Igen</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="even">
<td>Áthelyezés</td>
<td>Befejeződött</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Igen</td>
<td>Nem</td>
</tr>
<tr class="odd">
<td>Átvitel vagy folyamat</td>
<td>Üres</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="even">
<td>Átvitel vagy folyamat</td>
<td>A kanbankártya nem található</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="odd">
<td>Átvitel vagy folyamat</td>
<td>A kanbankártya megtalálható, de nincs hozzárendelve kanbanhoz</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="even">
<td>Feldolgozás</td>
<td><ul>
<li>Nem tervezett</li>
<li>Előkészítve</li>
<li>Folyamatban</li>
</ul></td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
<tr class="odd">
<td>Feldolgozás</td>
<td>Befejeződött</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
<td>Nem</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]