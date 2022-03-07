---
title: Összes áru mennyiségének hibája egy rendelés befejezésekor
description: Termelési rendelés befejezésekor és készként jelentéskor hibaüzenet jelenik meg a teljes áru mennyiségben. Ez az oldal bemutatja, hogy miért és hogyan lehet kijavítani a problémát.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476542"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Összes áru mennyiségének hibája egy termelési rendelés befejezésekor

## <a name="symptoms"></a>Tünetek

Amikor kész naplóként próbál feladni egy jelentést egy termelési rendelésen, a következő hibaüzenet jelenik meg:

> A termeléshez befejezettként jelentett összes hibátlan mennyiség %1 lesz. Az utolsó művelet visszajelzése 0,00 az összesből.

## <a name="cause"></a>Ok

Ez a probléma akkor fordul elő, ha az utolsó műveletekben könyvelt mennyiségek helytelenek voltak. Ha például a termelés elindult, de a beindítandó mennyiség nincs lefoglalva, az útvonalkártya naplósorok nélkül kerül feladása. A helyzet megerősítéséhez nyissa meg a termelési rendelést, majd a Művelet panel **Nézet** fülön válassza az **Útvonalkártya** lehetőséget.

## <a name="resolution"></a>Megoldás

A probléma megoldásához további naplókat adhat fel azokra a műveletekre vonatkozóan, amelyekhez a naplókat nem megfelelően könyvelték. Indítsa újra a termelési rendelést, és válassza a további naplók könyvelését. Ez a művelet nem indítja el a termelési rendelést, de könyveli a naplókat. Az útvonalkártyának ekkor meg kell jelennie a feladott mennyiségek között, és be kell tudnia fejezni a termelési rendeléseket.
