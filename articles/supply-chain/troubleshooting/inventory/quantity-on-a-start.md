---
title: Az elindított karanténutasításban szereplő mennyiség nem frissül a rendelés felosztása esetén
description: Amikor karanténutasítást hoz létre, és megpróbálja felosztani, a rendelési mennyiség nem frissül a fennmaradó megosztott mennyiséggel.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026588"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>Az elindított karanténutasításban szereplő mennyiség nem frissül a rendelés felosztása esetén

Tudásbáziscikk száma: 4613113

## <a name="symptoms"></a>Tünetek

Amikor karanténutasítást hoz létre, és megpróbálja felosztani, a rendelési mennyiség nem frissül a fennmaradó mennyiséggel a megosztás utám.

## <a name="resolution"></a>Felbontás

A rendszer nem módosítja az eredeti mennyiséget karanténutasításból, hogy nyomon követhető legyen az adott karanténutasításhoz létrehozott eredeti mennyiség. A rendszer azonban nyomon követi a karanténutasításból felosztott mennyiséget. Ehhez a nyomon követéshez egy `QuantityThatHasSplitIntoOtherQuarantineOrders` nevű adatbázismezőt használ. Ez a mező azonban nem jelenik meg a felhasználói felületen (UI).
