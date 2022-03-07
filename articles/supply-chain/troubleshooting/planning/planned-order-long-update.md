---
title: A tervezett rendelések frissítése hosszú időt vesz igénybe
description: A szükséglet mennyiségének és/vagy szállítási dátumának tervezett rendelésen történő frissítésekor általában rendelésenként legalább 30 másodpercet vesz igénybe a frissítés mentése
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476565"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>A tervezett rendelések frissítése hosszú időt vesz igénybe

## <a name="symptoms"></a>Tünetek

A szükséglet mennyiségének és/vagy szállítási dátumának tervezett rendelésen történő frissítésekor általában rendelésenként legalább 30 másodpercet vesz igénybe a frissítés mentése.

## <a name="resolution"></a>Megoldás

Ez egy ismert probléma a beépített fő tervezőmotorral. Ezt az okozza, hogy az anyagjegyzékstruktúrán keresztül a szerkesztések során automatikusan alá van bontva. Ezzel a problémával részletesebben a Tervezés optimalizálása című részben olvashat, ahol a tervező frissítheti és jóváhagyhatja a megfelelő rendeléseket, és szükség esetén tervezési futtatást indíthat el a mögöttes anyagjegyzékstruktúra tervezett rendeléseinek frissítéséhez.

A beépített fő tervezőmotorral a teljesítmény javításának egyik módja a következő lépések végrehajtása:

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon egy tervet.
1. Bontsa ki az **Időkorlátot napokban** gyorslapot.
1. Állítsa az **Alábontás** beállítást *Igen* értékre, és állítsa a beállítás alatti mezőt 0-ra (nulla).

> [!NOTE]
> Ez egyetlen napra korlátozza az alaptervben végrehajtott alábontások időszakát.
