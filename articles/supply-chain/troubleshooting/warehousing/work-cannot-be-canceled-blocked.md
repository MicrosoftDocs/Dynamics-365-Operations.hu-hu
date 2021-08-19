---
title: A munka nem vonható vissza, mert zárolva van
description: A munka nem vonható vissza, mert zárolva van
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a24f199484c7596189b19e4cddf344e9186c6044edd2906affca9b530de44168
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722199"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>A munka nem vonható vissza, mert zárolva van

Hibakód: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 munka nem szakítható meg, mert a következő ok miatt zárolva van: %2. A megszakítás előtt meg kell szűntetni a munka blokkolását.

## <a name="cause"></a>Ok

A munka zárolva van, ezért nem lehet megszakítani.

A **Munka** oldalon az **Általános** lapon a **Blokkolva** beállítás értéke *Igen*. Ez a beállítás azt jelzi, hogy a munka zárolva van. A **Blokkolási okok** lap mutatja, hogy miért blokkolták a munkát.

## <a name="resolution"></a>Felbontás

A munka zárolásának feloldásához válassza a **Blokkolási okok** lapot, majd hajtsa végre a következő lépések valamelyikét:

- Ha a **Munkazárolási ok** mező beállítása *Nem meghatározott ok*: A műveleti panel **Munka lapján** válassza a **Munka** csoportban válassza a **Munka zárolásának feloldása** lehetőséget.
- Ha a **Munka zárolásának oka** mező beállítása *Feldolgozási hullám*: A Műveletei panelen a **Kapcsolódó információk** lapon a **Kapcsolódó információk** csoportban válassza a **Hullám** lehetőséget. A Művelet panelen a **Hullámok** oldalon a **Hullám** lapon a **Hullám** csoportban válassza a **Hullámadatok karbantartása** lehetőséget.

## <a name="workaround"></a>Megkerülő megoldás

Ha az előző lépések nem oldják meg a problémát, a következő lépésekkel szakíthatja meg a munkát.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).
