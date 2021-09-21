---
title: A szállítási név nem szinkronizálódik a beszerzési rendelés szállítási címének módosítása után
description: A beszerzési rendelés fejlécében szereplő szállítási cím módosítása után a szállítási név nincs szinkronizálva
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
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476520"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>A szállítási név nem szinkronizálódik a beszerzési rendelés szállítási címének módosítása után

## <a name="symptoms"></a>Tünetek

Egy beszerzési rendelés fejlécében szereplő cím olyan címre módosul, amely nem a szállítási cím. Bár a cím frissítve van a beszerzési rendelésen, a szállítási név nem frissül a frissített cím alapján.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A kiválasztott cím besorolása szállítási cím kell legyen. Ellenkező esetben a szállítási név nem módosul a kiválasztott cím alapján.
