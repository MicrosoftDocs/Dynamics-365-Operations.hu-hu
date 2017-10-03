---
title: "Készpénzfizetési engedmények"
description: "A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára.  Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9d581a1d32a0df15e0b63e129d369d90aaa440d2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="cash-discounts"></a>Készpénzfizetési engedmények

[!include[banner](../includes/banner.md)]


A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára.  Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt. 

<a name="cash-discounts"></a>Készpénzfizetési engedmények
--------------

A vevők vagy szállítók készpénzfizetési engedményei a készpénzfizetési engedmények lapján is létrehozhatók. Azt is meghatározhatja a Következő engedmény kód mező használatával, hogy követik egymást az előző készpénzfizetési engedmény dátum lejárataként. További tájékoztatás, lásd "Példa: készpénzfizetési engedmények sorozata" később a témakörben. Ha a számla vagy jóváírási tranzakció (jóváírás vagy kifizetés) vagy mindekettő a jogi személy könyvelési pénznemében eltérő pénznemben vannak megadva, a készpénzfizetési engedmény számítása a kifizetések vagy jóváírások napja alapján az érvényes árfolyamának felhasználásával történik. Ha a számlák és jóváírási bizonylat különböző jogi személyek esetében vannak megadva, és ha a jogi személyek könyvelési pénznemei különböznek, az átváltási árfolyam a számla jogi személyétől származnak, mint a hitel dokumentum dátuma. További információkat, lásd "Példa: készpénzfizetési engedmények átváltási díjai" később a témakörben.
Fő számla készpénzfizetési engedmény alapértelmezési sorrendje
----------------------------------------------

Ha a számla kiegyenlítése időben megtörténik ahhoz, hogy a vevő készpénzfizetési engedményt kapjon, a program automatikusan feladja a készpénzfizetési engedményt a készpénzfizetési engedmény fő számlájára, az alábbi alapértelmezési prioritást figyelembe véve:
1.  A fő számla a vevői váltókiegyenlítési nyitott tranzakciók vagy a szállítói kiegyenlítési nyitott tranzakciók lapon a másik készpénzfizetésiengedmény-számla mezőben van meghatározva.
2.  A fő számla a számla adókódjához rendelt főkönyv feladó csoport Vevő készpénzfizetési engedmény mezőjében vagy a szállító készpénzfizetési engedmény mezőjében van meghatározva. Állítsa be a főkönyvi feladási csoportokat a főkönyvi feladási csoportok lapon, és rendelje hozzá az áfakódokhoz a forgalmi adó kódjainak lapján.
3.  A fő feladási számla a készpénzfizetési engedmények lapján vagy a vevő Fő számlája engedmények mezőben vagy a Szállító Fő számlája mezőben a kiegyenlített számláko szereplő készpénzfizetési engedmény kódokhoz.
4.  A készpénzfizetési engedmények fő számlája az automatikus tranzakciók lapok számláján van meghatározva.

## <a name="example-series-of-cash-discounts"></a> Példa: Készpénzfizetési engedmények sorozatai
Állítson be három kódot a készpénzfizetési engedményekhez a következők szerint:
-   5D10% kód - 10%-os készpénzfizetési engedmény, amikor az összeg 5 napon belül kerül kiegyenlítésre.
-   10D5% kód - 5%-os készpénzfizetési engedmény, ha az összeg 10 napon belül kerül kiegyenlítésre.
-   14D2% kód - 2%-os készpénzfizetési engedmény, ha az összeg 14 napon belül kerül kiegyenlítésre.

A Következő engedmény kódja mezőben:
-   Az 5D10% kódnál válassza a 10D5% elemet.
-   A 10D5% kódnál válassza a 14D2% elemet.
-   A 14N2% kódnál hagyja üresen a Következő engedménykód mezőt.

A készpénzfizetési engedmény három kódja követi egymást mivel a fizetési dátum meghaladja a számlán szereplő előző készpénzfizetési engedmény dátumát. Egy készpénzfizetési engedmény csak akkor van engedélyezve, amikro a számla ki van egyenlítve, azon alapul, hogy melyik készpénzfizetési engedmény dátuma felel meg a készpénzfizetési engedmények sorozatában.

## <a name="example-exchange-rates-for-cash-discounts"></a> Példa: Készpénzfizetési engedmények átváltási díjai
A jogi személy könyvelési pénzneme EUR és a következő árfolyamok USD-ben vannak megadva:
-   február 1 = 110
-   március 1 = 80

Február 15-én adnak fel egy 20D2%-os készpénzfizetési engedménnyel rendelkező 1000 USD-s számlát. A számla összege a könyvelési pénznemben 1100 EUR. A számlaösszegből 980 USD kifizetése történik meg március 1-jén. A készpénzfizetési engedmény összege 20 USD. A fizetés könyvelési pénznemének összege 784 EUR. A készpénzfizetési engedmény összegének a könyvelési pénznemben történő kiszámítása március 1-jei átváltási árfolyam alapján történik: 20 \* 80 / 100 = 16 EUR.
| **Megjegyzés**                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ha a részfizetés beállítás készpénzfizetési engedmény számítása van kiválasztva a Számla kötelezettségek paramétereinek vagy a Kötelezettségi paramétereinek lapjain, az az átváltási díj használatos, amely hatással van minden egyes részlet fizetés dátumára. |

 
=

 




