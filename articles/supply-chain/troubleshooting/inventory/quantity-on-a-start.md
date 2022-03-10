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
ms.openlocfilehash: 4625570cb706199dca78f23b1864ca1d81cc66e896cf10d6d5f16cf1a9d1dc16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713494"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>Az elindított karanténutasításban szereplő mennyiség nem frissül a rendelés felosztása esetén

Tudásbáziscikk száma: 4613113

## <a name="symptoms"></a>Tünetek

Amikor karanténutasítást hoz létre, és megpróbálja felosztani, a rendelési mennyiség nem frissül a fennmaradó mennyiséggel a megosztás utám.

## <a name="resolution"></a>Felbontás

A rendszer nem módosítja az eredeti mennyiséget karanténutasításból, hogy nyomon követhető legyen az adott karanténutasításhoz létrehozott eredeti mennyiség. A rendszer azonban nyomon követi a karanténutasításból felosztott mennyiséget. Ehhez a nyomon követéshez egy `QuantityThatHasSplitIntoOtherQuarantineOrders` nevű adatbázismezőt használ. Ez a mező azonban nem jelenik meg a felhasználói felületen (UI).
