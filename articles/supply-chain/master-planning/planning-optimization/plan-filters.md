---
title: Szűrők alkalmazása egy tervre
description: Ez a témakör azt mutatja be, hogyan lehet szűrőket használni egy terven, amikor a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ff9c9f875368fcc4dd62b9c188d489e20a5c7960
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773975"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="apply-filters-to-a-plan"></a>Szűrők alkalmazása egy tervre

A tervezés optimalizálása funkció használata esetén szűrőket alkalmazhat a tervre. A terv szűrője mindig az Alaptervezés futtatásakor lesz alkalmazva. A tervszűrő akkor hasznos, ha egy tervet egy adott cikkcsoportra szeretné korlátozni, és szeretne meggyőződni róla, hogy a létrejövő Alaptervezés részeként nem szerepelnek más cikkek.

Ha a tervszűrőt alkalmazta, és az alaptervezés futtatása során a futásidejű szűrő is alkalmazva van, akkor a tervezési futtatásban csak a két szűrő metszete szerepel.

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
