---
title: Pénznem-átváltási problémák a kereskedelmi megállapodásoknál
description: A kereskedelmi megállapodás árait nem számítja újra a program a beszerzési rendelés pénzneme használatával, ha az eltérő
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476516"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Pénznem-átváltási problémák a kereskedelmi megállapodásoknál

## <a name="symptoms"></a>Tünetek

A kereskedelmi megállapodás árait nem számítja újra a program a beszerzési rendelés pénzneme használatával, ha az eltérő.

## <a name="resolution"></a>Megoldás

Az *Általános pénznem* funkció lehetővé teszi az árak és engedmények definiálását egy pénznemben. Ezt követően a szükséges módon konvertálhat más pénznemekre. Ezenkívül az átváltás után a funkcióval automatikusan alkalmazhat intelligens kerekítést.
