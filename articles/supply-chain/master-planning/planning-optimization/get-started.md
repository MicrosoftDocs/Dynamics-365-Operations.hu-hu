---
title: Első lépések a tervezési optimalizálással
description: Ez a témakör bemutatja, hogyan kezdje el használni a tervezési optimalizáció funkciót.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
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
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773971"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Első lépések a tervezési optimalizálással

A tervezés optimalizálása funkció jelenleg nem támogatja az összes olyan funkciót, amely a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba épített tervezési motorban rendelkezésre áll. Ezért fontos, hogy meggyőződjön, hogy a tervezésoptimalizálásban jelenleg elérhető szolgáltatáskészlet kielégíti-e a követelményeket. Alapértelmezés szerint a Tervezés optimalizálása funkció nincs bekapcsolva a Dynamics Lifecycle Services (LCS) modulban. Ennek megfelelően lehetősége van arra, hogy az értékelést a bekapcsolás előtt végezze el.

Végül a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management tervezési motorját.

A tervezés optimalizálása előtt kifejezetten ajánljuk, hogy értékelje a tervezésoptimalizálás illeszkedési elemzésének eredményeit. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licenckezelés

Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.

### <a name="install-the-add-in"></a>Telepítse a bővítményt

A Tervezés optimalizálása modul használatához telepíteni kell a Tervezés optimalizálása bővítményt a következőhöz: Dynamics 365 Supply Chain Management. A bővítményt a LCS-projektből érheti el, és a Supply Chain Management felhasználói felületéről (UI) be lehet kapcsolni a tervezés optimalizálása funkcióját.

1. Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.
1. Lépjen a **Teljes részletek** elemre.
1. Válassza a **karbantartás** lehetőséget, vagy görgessen a **környezeti bővítmények** gyorslapra.
1. Válassza az **Új bővítmény telepítése** lehetőséget.
1. Válassza a **Tervezés optimalizálása** lehetőséget.
1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
1. Válassza a **Telepítés** parancsot.

### <a name="planning-optimization-integration"></a>A tervezésoptimalizálás integrációja

Annak konfigurálásához, hogy a Tervezésoptimalizálás bővítményt használja-e a rendszer az alaptervezéshez, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezésoptimalizálás integrációja** \> **Integrációs paraméterek** pontot.

#### <a name="connection-status"></a>Kapcsolat állapota

A kapcsolat állapota jelzi a kapcsolat aktuális állapotát a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között. A következő táblázat mutatja a lehetséges értékeket.

| Kapcsolat állapota | Leírás | Használható a Tervezésoptimalizálás? |
|---|---|---|
| Csatlakoztatva | A rendszer kapcsolatot létesített a Tervezésoptimalizálás és a Supply Chain Management között. | Igen |
| Kapcsolat engedélyezése | Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat bekapcsolási kérelme. | Nem |
| Leválasztva | Nincs kapcsolat a tervezés optimalizálása szolgáltatással. A kapcsolat a következő témakörben leírtak szerint a LCS-ről kapcsolható be. | Nem |
| Kapcsolat letiltása | Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat kikapcsolási kérelme. | Nem |
| Állapot lekérése | A rendszer a tervezés optimalizálása szolgáltatásból származó állapotadatokra várakozik. | Nem |

#### <a name="the-use-planning-optimization-option"></a>A Tervezésoptimalizálás beállítás használata

A **Tervezés optimalizálása használata** beállítás határozza meg, hogy melyik tervezési motor használható az alaptervezéshez:

- **Igen** – a tervezésoptimalizálás az alaptervezéshez használatos.
- **Nem** – Az alaptervezéshez a Supply Chain Management beépített tervezési motorja használatos.

> [!NOTE]
> Ha meglévő tervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, elindulnak, miközben a **Tervezésoptimalizálás használata** beállítás értéke **Igen**, a feladatok sikertelenek lesznek.

### <a name="integration-with-the-setup"></a>Integráció a beállítással

Ha a Tervezésoptimalizálás előzetes verziója be van kapcsolva, akkor az alaptervezést a rendszer a Tervezésoptimalizálás bővítménnyel végzi. Ebben az esetben az Alaptervezés eredményeit és funkcióit érinti a program.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Az előzetes verzió feltételei és kikötései](https://go.microsoft.com/fwlink/?linkid=2015274)

[Tervezés optimalizálása – áttekintés](planning-optimization-overview.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)
