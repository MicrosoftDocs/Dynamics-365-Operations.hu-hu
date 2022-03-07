---
title: A kereskedelmi megállapodás feltételei nem vonatkoznak az importált rendeléssorokra
description: A kereskedelmi megállapodási árak és engedmények nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra
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
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476580"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>A kereskedelmi megállapodás feltételei nem vonatkoznak az importált rendeléssorokra

## <a name="symptoms"></a>Tünetek

Az értékesítési vagy beszerzésirendelés-sorokra vonatkozó kereskedelmi megállapodások nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra. Ugyanezek a kereskedelmi megállapodások azonban olyan értékesítési vagy beszerzésirendelés-sorokra vonatkoznak, amelyek manuálisan jönnek létre.

## <a name="cause"></a>Ok

Ha az adatkezelésen keresztül importált beszerzésirendelés-sorok már tartalmazzák az árak adatait, akkor a kereskedelmi megállapodás nem lesz újraértékelve ezekhez a sorokhoz. Ha például a **Sorengedmény százaléka** vagy az ár-és az engedményértékeket bármelyike egy sorhoz be van állítva, akkor a kereskedelmi megállapodásokat nem keresi a program ehhez a sorhoz.

## <a name="workaround"></a>Megkerülő megoldás

Ez a viselkedés várható, és az értékesítési rendelésekhez és a beszerzési rendelésekhez hasonló.

Megoldásként importálja a beszerzési rendelés sorait az áradatok megadása nélkül. A kereskedelmi megállapodások ekkor alkalmazva lesznek, és a beszerzési rendelési sorok a meghatározott kereskedelmi megállapodások alapján lesznek frissítve.
