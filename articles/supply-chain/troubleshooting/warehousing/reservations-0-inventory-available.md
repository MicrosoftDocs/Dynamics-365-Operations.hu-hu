---
title: Nem lehet készletfoglalásokat végezni, mert 0,00 érhető el.
description: Ha hibaüzenet jelenik meg, a rendszer nem tud foglalást tenni, mert a készletben csak 0,00 érhető el. Ezt a problémát valószínűleg a nyitott munka okozza.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476583"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>A rendszer nem végezhet készletfoglalásokat, mert 0,00 érhető el a készletben

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz. A következő hibaüzenetet kapja:

> Tényleges aktuális Telephely=%1, Raktár=%2, Készletállapot=Elérhető, Kötegszám=%3, Tulajdonos=%4: %5 nem foglalható le, mert csak 0,00 érhető el a készletben.

## <a name="resolution"></a>Megoldás

Ezt a problémát valószínűleg a nyitott munka okozza. Vagy hajtsa végre a munkát vagy fogadja a munka létrehozása nélkül. Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget. Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.
