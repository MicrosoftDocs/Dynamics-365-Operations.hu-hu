---
title: Tervelőzmények és tervezési naplók megtekintése
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni a tervezés optimalizálása funkció által kezdeményezett tervezési feladatok előzményeit.
author: ChristianRytt
ms.date: 10/30/2019
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187247"
---
# <a name="view-plan-history-and-planning-logs"></a>Tervelőzmények és tervezési naplók megtekintése

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megtekinteni a tervezés optimalizálása funkció által kezdeményezett tervezési feladatok előzményeit a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

A terv előzményeinek megtekintéséhez nyissa meg a tervet az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervek** pontban, majd válassza ki az **Előzmények** elemet. Az előzményben felsorolva láthatók a kiválasztott tervekhez tartozó feladatok. A lista tartalmazza a befejezett és az aktív feladatokat.

A Tervezési optimalizálási alaptervezés feladatelőzményei csak alaptervenként legfeljebb 60 rekordot tartnak fent. Amikor új alaptervezési számítást futtat, annak a tervnek a legkorábbi előzményrekordja törlődik.

A feladatok kezdési időpontjának és állapotának megtekintésén kívül az adott feladatra vonatkozó naplót is megtekintheti. A napló további információkat és figyelmeztetéseket tartalmaz. Nem minden feladatnak van naplója. A feladathoz tartozó napló megtekintéséhez válassza ki a **Napló** elemet. A naplóbejegyzések csak a munka befejezése után 30 napig tárolódnak, azokat automatikusan törli a rendszer.

## <a name="related-resources"></a>Kapcsolódó erőforrások

- [Tervezési optimalizálás áttekintése](planning-optimization-overview.md)
- [Tervezési optimalizálás kezdő lépései](get-started.md)
- [A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)
- [Szűrők alkalmazása egy tervre](plan-filters.md)
- [Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]