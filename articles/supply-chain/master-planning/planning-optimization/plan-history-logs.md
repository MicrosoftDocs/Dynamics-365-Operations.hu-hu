---
title: Tervelőzmények és tervezési naplók megtekintése
description: Ez a cikk bemutatja a tervezési feladatok előzményeinek megtekintését.
author: t-benebo
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ab469686a009364bf53cb963506fd2107075a283
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740931"
---
# <a name="view-plan-history-and-planning-logs"></a>Tervelőzmények és tervezési naplók megtekintése

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet megtekinteni a Microsoft tervezési munkáinak előzményeit Dynamics 365 Supply Chain Management.

A terv előzményeinek megtekintéséhez nyissa meg a tervet az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervek** pontban, majd válassza ki az **Előzmények** elemet. Az előzményben felsorolva láthatók a kiválasztott tervekhez tartozó feladatok. A lista tartalmazza a befejezett és az aktív feladatokat.

A rendszer legfeljebb 60 előzményrekordot tart meg alaptervenként, és törli a 30 napnál régebbi rekordokat. A rendszer minden alkalommal, amikor új alaptervezési számítást futtat, új előzményrekordot hoz létre, majd szükség szerint tisztítja a legrégebbi rekordokat.

A feladatok kezdési időpontjának és állapotának megtekintésén kívül az adott feladatra vonatkozó naplót is megtekintheti. A napló további információkat és figyelmeztetéseket tartalmaz. Nem minden feladatnak van naplója. A feladathoz tartozó napló megtekintéséhez válassza ki a **Napló** elemet. A naplóbejegyzések csak a munka befejezése után 30 napig tárolódnak, azokat automatikusan törli a rendszer.

Ha az alaptervezés feldolgozásának beállításakor engedélyezve volt a **Kötegelt feldolgozás** beállítás a **Futtatás a háttérben** gyorslapon, a kötegelt feladat naplója további információkat is megjeleníti az alaptervezés futtatása során keletkező figyelmeztetésekkel és hibákkal kapcsolatban. Az automatikus megerősítési hibák például csak a kötegelt feladatok naplójában vannak rögzítve. Az **Előzmények** oldalon nem jelennek meg a naplókban.

Az alaptervezés futtatásakor történt automatikus megerősítési hibák és egyéb figyelmeztetések vagy hibák megtekintéséhez kövesse az alábbi lépéseket.

1. Ugorjon a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** pontra.
1. Keresse meg és válassza ki azt a rekordot, amely a kívánt alaptervezési futtatásnak felel meg. (Például a **Munkaköri leírás** mező az *Alaptervezéssel* kezdődhet.)
1. Hajtsa végre az alábbi lépések valamelyikét attól függően, hogy a *továbbfejlesztett űrlapot* vagy az *örökölt (nem továbbfejlesztett) űrlapot* használja a **Kötegelt feladatok** laphoz:

    - Ha a továbbfejlesztett űrlapot használja: A műveleti panelen válassza ki a **Kötegelt feladatok előzményei** lehetőséget. Ezután a **Kötegelt feladatok előzményei** oldalon, a Műveleti panelen válassza a **Napló** lehetőséget.
    - Ha a régi űrlapot használja: A műveleti panelen válassza ki a **Kötegelt feladatok** lapon a **Napló** lehetőséget.

1. Az **Üzenet részletei** ablaktábla megnyitásához válassza ki az **Üzenet részletei** lehetőséget ahol megtekintheti a feldolgozás során rögzített összes figyelmeztetést és hibát.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
