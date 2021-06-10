---
title: Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján
description: Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049471"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján

Tudásbáziscikk száma: 4612572

## <a name="symptoms"></a>Tünetek

Az alaptervezés kötegelt feladatában szereplő cikkeket a cikkfedezeti tábla kapcsolódó rekordjainak értékei alapján szeretné szűrni. (A cikkeket például a **Szállító** és/vagy a **Fedezeti csoport** értéke alapján lehet érdemes szűrni). A kötegelt feladat szűrőbeállítása lehetővé teszi, hogy összekapcsolást hozzon létre a **Cikkek** táblából a **Cikkfedezet** táblába, majd megadja a lekérdezésben lévő cikkfedezeti táblából származó mezőértékeket. A beállítás befejezése után azonban a rendszer továbbra is a teljes cikkfedezethez hoz létre tervezett rendeléseket, nem csak a cikkfedezeti táblából származó magadott mezőértékeknek megfelelő cikkekhez.

## <a name="resolution"></a>Megoldás

A kötegelt feladatok szűrője csak cikkekre tud szűrést végezni. Bár lehet összekapcsolást hozzáadni a **Cikkfedezet** táblához, az adott táblánál megadott szűrőbeállítások nincsenek hatással a lekérdezés kimenetére. Futásidőben a rendszer minden fedezeti csoporthoz és a szűrt cikkek összes változatához futtat tervezést. Ha egy cikk már szerepel a futtatásban, a cikkszűrőben szereplő fedezeti csoportok nincsenek hatással a tervezés kimenetére.
