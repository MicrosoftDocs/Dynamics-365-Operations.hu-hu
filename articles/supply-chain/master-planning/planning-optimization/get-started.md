---
title: Első lépések a tervezési optimalizálással
description: Ez a témakör bemutatja, hogyan kezdje el használni a tervezési optimalizáció funkciót.
author: ChristianRytt
manager: tfehr
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4f9124e824a0b6d5035b2567cb19c2c494390d55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213515"
---
# <a name="get-started-with-planning-optimization"></a>Első lépések a tervezési optimalizálással

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

A tervezés optimalizálása funkció jelenleg nem támogatja az összes olyan funkciót, amely a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba épített tervezési motorban rendelkezésre áll. Ezért fontos, hogy meggyőződjön, hogy a tervezésoptimalizálásban jelenleg elérhető szolgáltatáskészlet kielégíti-e a követelményeket. Alapértelmezés szerint a Tervezés optimalizálása funkció nincs bekapcsolva a Dynamics Lifecycle Services (LCS) modulban. Ennek megfelelően lehetősége van arra, hogy az értékelést a bekapcsolás előtt végezze el.

Végül a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management tervezési motorját.

A tervezés optimalizálása előtt kifejezetten ajánljuk, hogy értékelje a tervezésoptimalizálás illeszkedési elemzésének eredményeit. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licenckezelés

Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.

### <a name="install-the-add-in"></a>Telepítse a bővítményt

A Tervezés optimalizálása modul használatához telepíteni kell a Tervezés optimalizálása bővítményt a következőhöz: Dynamics 365 Supply Chain Management. A bővítményt a LCS-projektből érheti el, és a Supply Chain Management felhasználói felületéről (UI) be lehet kapcsolni a tervezés optimalizálása funkcióját.

> [!NOTE]
> A tervezésoptimalizálás követelménye egy LCS-kompatibilis magas rendelkezésre állású környezet (nem OneBox környezet), a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával.

1. Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.
1. Lépjen a **Teljes részletek** elemre.
1. Görgessen le a **Környezeti bővítmények** gyorslapra.
1. Válassza az **Új bővítmény telepítése** lehetőséget.
1. Válassza a **Tervezés optimalizálása** lehetőséget.
1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
1. Válassza a **Telepítés** parancsot.
1. A **Környezeti bővítmények** gyorslapon látnia kell, hogy a Tervezési optimalizálás telepítése folyamatban van.
1. Néhány perc múlva a **Telepítés** felirat erre módosul: **Telepítve** (előfordulhat, hogy frissíteni kell az oldalt). A telepítés befejezésekor készen áll a Tervezési optimalizálás funkció aktiválására a Dynamics 365 Supply Chain Management alkalmazásban.

### <a name="planning-optimization-integration"></a>A tervezésoptimalizálás integrációja

Annak konfigurálásához, hogy a Tervezési optimalizálás bővítményt használja-e a rendszer az alaptervezéshez, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezési optimalizálás paraméterei** lehetőséget.

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
