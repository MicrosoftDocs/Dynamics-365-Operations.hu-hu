---
title: A Munka zárolva marad
description: A Munka zárolva marad
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 898390c78bb26fb8a44f77a10ad27a00720f7d1a3396cec5fff10e9d6b93364d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768570"
---
# <a name="work-remains-blocked"></a>A Munka zárolva marad

Hibakód: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 munka zárolva marad, mert a kapcsolódó %2 hullám állapota %3.

## <a name="cause"></a>Ok

A munka feldolgozása jelenleg folyamatban van egy hullámban, és nem lehet feloldani a zárolását az alábbi feltételek egyikének megfelelően:

- A **Blokkolási okok** lapon egy vagy több sor **Munkablokkolási ok** mezőjében a *Feldolgozás hullám* van beállítva.
- Amikor a **Hullám** lehetőséget választja ki a **Kapcsolódó információk** csoportban a Műveleti ablaktábla **Kapcsolódó információk** panelén a **Hullám állapota** mező *Feldolgozás* értékre van állítva.

## <a name="resolution"></a>Felbontás

A Művelet ablaktábla **Kapcsolódó információk** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullám** elemet. A Művelet panelen a **Hullámok** oldalon a **Hullám** lapon a **Hullám** csoportban válassza a **Hullámadatok karbantartása** lehetőséget.

## <a name="workaround"></a>Megkerülő megoldás

Ha az előző lépések nem oldják meg a problémát, a következő lépésekkel szakíthatja meg a munkát.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).
