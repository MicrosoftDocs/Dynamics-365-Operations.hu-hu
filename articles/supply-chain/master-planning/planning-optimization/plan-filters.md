---
title: Szűrők alkalmazása egy tervre
description: Ez a témakör azt mutatja be, hogyan lehet szűrőket használni egy terven, amikor a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 7b605f9826d2116f6f52a4b880f4fb5bd24cfdd0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813051"
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
> Lehetőleg ne állítson be tervszűrőt olyan terven, amelyet az **Alaptervezés paraméterei** oldalon **Aktuális dinamikus alaptervként** állított be. Ellenkező esetben a rendszer a szűrt cikkekre korlátozza a dinamikus alapterv funkcióját. Ha például a nettó követelmények olyan cikkeknél frissülnek, amelyek nem részei a tervszűrőnek, akkor nem jön létre eredmény.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Tervezés optimalizálása – áttekintés](planning-optimization-overview.md)

[Első lépések a tervezési optimalizálással](get-started.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]