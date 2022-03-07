---
title: Hiba a Készként jelentett állapotról Befejezett állapotra való módosításakor
description: Előfordulhat, hogy hiba jelenik meg a termelési rendelés készként jelentett állapotról Befejezett állapotra való módosításakor. Ez az oldal bemutatja, hogy hogyan lehet mérsékelni a problémát.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476558"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Hiba a termelési rendelés készként jelentett állapotról Befejezett állapotra való módosításakor.

## <a name="symptoms"></a>Tünetek

Amikor egy termelési rendelés állapota Készként jelentve befejezéskor értékről Befejezve értékre változik, a következő hibaüzenetek egyike jelenhet meg:

> Frissítési ütközés. Az elszámolóár nem egyezik meg a frissítés utáni pénzügyi készletértékkel.

> Kritikus hiba történt az InventCostMovement.checkVariance függvényben.

## <a name="cause"></a>Ok

A probléma oka az, hogy a háttéradatokat egy másik folyamat módosította. A folyamat legfeljebb ötször próbálja meg frissíteni az adatokat. Ha az ütközés öt kísérlet után is fennáll, a fenti hibaüzenetek egyike jelenik meg.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A probléma enyhítése érdekében folytassa a kötegelt feladatot. A futtatásnak be kell fejeződnie.

Ha a kötegelt feladat a folytatás után folyamatosan sikertelen, ellenőrizze, hogy a főkönyv alapértelmezett pénznemének kerekítési pontossága megfelel-e az InventSum tábla értékére alkalmazott kerekítésnek. Ha a kerekítési pontosság nem megfelelő értékre módosult, valószínűleg vissza kell állítania egy megfelelő értékre. Keresse meg a **ModifiedDateTime** lehetőséget. Ebben az esetben az érték általában azt mutatja, hogy a kerekítési pontosság nemrég megváltozott.
