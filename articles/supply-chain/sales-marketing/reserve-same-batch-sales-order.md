---
title: Egy értékesítési rendelés foglalása ugyanazon kötegből
description: Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből.
author: Henrikan
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d4f3ee5d99648155e663c9ad0849b0b9ae3f80e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576616"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Egy értékesítési rendelés foglalása ugyanazon kötegből

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből.

Az ugyanazon kötegből való foglalás funkcióval egy értékesítési rendelést a készlet egyetlen adott kötegéből foglalhatja le. Tegyük fel, hogy egy tapétát rendelő vevő azt szeretné, hogy a teljes rendelést egy adott kötegből vagy adagból szállítsák neki, nehogy eltérő legyen a tekercsek minősége. Ha egyazon kötegből szeretne foglalni, az alábbi beállításoknak kell aktívnak lenniük a termékhez rendelt cikkmodellcsoportban, a nyomon követési dimenzióban és a tárolási dimenziócsoportban:

- **Cikkmodellcsoportok** – A cikkmodellcsoportnál be kell jelölni az **Azonos köteg kiválasztása** és az **Összesített követelmény** mezőket a **Foglalás** mezőcsoportban, a készletirányelvek között.
- **Nyomon követési dimenziócsoportok** – A nyomon követési dimenziócsoportoknál be kell jelölni a kötegszámhoz tartozó **Fedezeti terv dimenziónként** mezőt.
- **Tárolási dimenziócsoportok** – A tárolási dimenziócsoportoknál be kell jelölni a **Fedezeti terv dimenziónként** mezőt a **Hely** és a **Raktár** vonatkozásában.

Amikor ugyanazon kötegből foglalja egy értékesítési rendelés termékeit, a rendszer megpróbálja a teljes rendelt mennyiséget egyetlen készletkötegből foglalni. Az esetleges specifikus kötegattribútumokat is figyelembe veszi. Ha a mennyiség rendelhető be egyetlen kötegől, akkor az **Azonos köteg foglalása miatti ütközés** lap jelenik meg. Ez az oldal leírja a problémákat, és a lehetséges megoldásokat is, amelyekkel folytathatja a foglalást. A következő események akadályozhatják meg a tétel foglalását:

- A kötegrendelkezési kódnál **Foglalás letiltása** van beállítva a **Zárolva** állapotú értékesítésekre.
- A köteg a lejárati dátum alapján és a vevői eladhatósági napok alapján már lejárt. A cikk még nem alkalmas lefoglalásra, ha a cikkmodellcsoportja FEFO dátumvezérelt, és a komissiózási feltétel a lejárati nap.
- A köteg eltarthatósági napjaiból fennmaradó idő nem elégséges, a lejárati dátum és a szavatosság dátuma alapján, illetve a vevői eladhatósági napok alapján.

Az engedélyezett **Raktárkezelési folyamatokkal** rendelkező tárolási csoportokhoz társított cikkek esetében a meghatározott kötegszámot foglalhat egy foglalási hierarchia használatával, ahol a kötegszám készletdimenzió a hely dimenzió fölött van megadva. Az ilyen típusú foglalási hierarchia ismertebb neve *Kötegelt a \[hely\] felett* foglalási hierarchia. Az értékesítési és átmozgatási rendelés sorainak **Kötegelt foglalás** lapja is lehetővé teszi több sor kiválasztását és foglalását a rendelkezésre álló kötegszám alapján. Ha további tájékoztatást szeretne arról, hogy mi a teendő, ha olyan foglalási hierarchiát használ, amelyben a kötegszám dimenzió a hely alatt található (*Kötegelt a \[hely\] alatt*), tekintse meg a [Rugalmas raktárszintű dimenzió foglalási irányelv](../warehousing/flexible-warehouse-level-dimension-reservation.md) dokumentumot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
