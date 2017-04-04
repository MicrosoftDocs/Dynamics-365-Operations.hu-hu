---
title: "Forgalmi adókifizetések és kerekítési szabályok"
description: "Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: 8f28ab4ea0fed975edbed60ddf5630d2d26ba0bc
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-payments-and-rounding-rules"></a>Forgalmi adókifizetések és kerekítési szabályok

Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.

Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak. Ez a kiegyenlítési futtatásával elvégezhető, és a forgalmi adó lap forgalmi adó folyamat feladni. Időtartamra vonatkozó forgalmi adót kiegyenlítő áfa számlák és a forgalmi adó egyenlege az ÁFA elszámolási számlára könyveli. A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon. 

A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.

Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.

### <a name="example"></a>Példa:

Az időszak teljes áfája -98,765.43 követel egyenleget mutat. A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett. Emiatt a jogi személy pénzzel tartozik az adóhatóságnak. 

A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti. Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:

1.  Kattintson az adó &gt;közvetett adók &gt;áfa &gt;az adóhatóságok
2.  Az Általános gyorslapon Kerekítési képernyő mezőjében kiválasztja a Normál lehetőséget.
3.  A Lekerekítés mezőben ezt adja meg: 1,00.
4.  Amikor az áfa kifizetése esedékes az adóhatóság felé, megnyitja az Adók kiegyenlítése és feladása lapot. (Kattintson az adó &gt;nyilatkozatok &gt;áfa &gt;rendezésére és a forgalmi adót könyveli.)
5.  Az áfakiegyenlítési számlán az adókötelezettség, amely 98.765,43, 98.765-re lesz kerekítve.

Az alábbi táblázat bemutatja, hogyan kerekítjük a 98.765,43 összeget az egyes kerekítési módok használatával az Adóhatóságok lapon, a Kerekítési képernyő mezőjében.

| Kerekítési képernyőopció                | Lekerekítési érték = 0,01 | Lekerekítési érték = 0,10 | Lekerekítési érték = 1,00 | Lekerekítési érték = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normál                              | 98.765,43              | 98.765,40              | 98.765,00              | 98.800,00                |
| Lefelé                            | 98.765,43              | 98.765,40              | 98,765.00              | 98.700,00                |
| Felkerekítés                         | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |
| Saját előny, egy követel egyenleghez | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| Saját előny, egy tartozik egyenleghez  | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |

> [!NOTE]                                                                                  
> Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik. 

További tudnivalókért lásd: [áfa – áttekintés](indirect-taxes-overview.md). 


