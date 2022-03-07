---
title: A beszerzési rendelések nem tükrözik a jogi személy nyelvi beállításait.
description: A beszerzési rendelésen szereplő terméknév a rendszer nyelvén jelenik meg a beszerzési rendelés létrehozásához használt jogi személyhez megadott nyelv helyett
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476541"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>A beszerzési rendelések nem tükrözik a jogi személy nyelvi beállításait.


## <a name="symptoms"></a>Tünetek

A beszerzési rendelésen szereplő terméknév a rendszer nyelvén jelenik meg a beszerzési rendelés létrehozásához használt jogi személyhez megadott nyelv helyett.

## <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A rendszer nyelvét állítsa *EN-US* (amerikai angol) értékre.
1. Győződjön meg róla, hogy van olyan termék, ahol az *EN-US* és *DE* (német) nyelvek vannak fenntartva a termék név fordításaihoz.
1. Jogi személy nyelvét módosítsa *DE* értékre.
1. A jogi személyben, ahol a nyelv beállítása *DE* hozzon létre egy beszerzési rendelés, ami tartalmazza a terméket.
1. Figyelje meg, hogy a termék neve továbbra is az angol nyelven jelenik meg (a rendszer nyelvén).

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A beszerzési rendeléseken a termék mindig a rendszer nyelvén jelenik meg. A beszerzési rendelés nyelvét a rendszer a visszaigazolási napló létrehozásakor használja.
