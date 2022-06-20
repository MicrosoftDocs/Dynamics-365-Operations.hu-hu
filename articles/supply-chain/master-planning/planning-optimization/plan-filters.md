---
title: Szűrők alkalmazása egy tervre
description: Ez a cikk bemutatja, hogy hogyan lehet szűrőket használni a terveken a tervezési optimalizálási funkció használata esetén.
author: t-benebo
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2df379be0876225bc7b0301d21f4e6660b04eb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875304"
---
# <a name="apply-filters-to-a-plan"></a>Szűrők alkalmazása egy tervre

[!include [banner](../../includes/banner.md)]

A tervezés optimalizálása funkció használata esetén szűrőket alkalmazhat a tervre. A **Tervszűrő** mindig az alaptervezés futtatásakor lesz alkalmazva. A **Tervszűrő** akkor hasznos, ha egy tervet egy adott cikkcsoportra szeretné korlátozni, és szeretne meggyőződni róla, hogy a létrejövő alaptervezés részeként nem szerepelnek más cikkek.

Ha a **tervszűrőt** alkalmazta, és az alaptervezés futtatása során a futásidejű szűrő is alkalmazva van, akkor a tervezési futtatásban csak a két szűrő metszete szerepel.

A **tervszűrőt** a Tervezési optimalizálás során az **alaptervekből** is el lehet érni.

## <a name="example-scenario"></a>Példaforgatókönyv

Az A, B és C cikkeket tartalmazó tervszűrő van beállítva. Az alaptervezés-futásokat lefuttatják ugyanerre a tervre, de más futásidejű szűrőket alkalmaznak:

- **A D cikket tartalmazó futásidejű-szűrő:** Nincsenek tervezett cikkek, mert nincs közös metszete a tervszűrőnek és a futásidejű szűrőnek.
- **Futásidejű szűrő, amely tartalmazza az A és D elemet**: csak az A elem szerepel a tervezés futtatásakor, mivel a D-es elem nem része a terv szűrőnek.
- **Futásidejű szűrő, amely tartalmazza a B elemet**: csak a B elem szerepel a tervezés futtatásakor, és megmarad a korábbi tervezés kimeneteként az A elem is.
- **Az összes cikket tartalmazó futásidejű szűrő (üres szűrő)** : az A, a A és a C cikkek szerepelnek a tervezés futtatásakor, és korábbi tervezési kimenet A és B eleme felülíródik.

> [!NOTE]
> Ha **az** **Alaptervezés** paraméterei lapon az Aktuális dinamikus alapterv beállítású tervhez beállít egy tervszűrőt, akkor a dinamikus alapterv funkció a szűrt cikkekre korlátozódik. Ha például a nettó követelmények olyan cikkeknél frissülnek, amelyek nem részei a tervszűrőnek, akkor nem jön létre eredmény.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Tervezés optimalizálása – áttekintés](planning-optimization-overview.md)

[Első lépések a tervezési optimalizálással](get-started.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
