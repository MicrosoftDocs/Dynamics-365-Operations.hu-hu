---
title: "Forgalmi adókifizetések és kerekítési szabályok"
description: "Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 13470282efc6b9135e86355cf8071b841aad3071
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a>Forgalmi adókifizetések és kerekítési szabályok

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.

Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak. Ez a Forgalmi adó oldalon a forgalmi adó rendezése és feladása folyamat használatával végezhető el. Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára. A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon. 

A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.

Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.

### <a name="example"></a>Példa:

Az időszak teljes áfája -98,765.43 követel egyenleget mutat. A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett. Emiatt a jogi személy pénzzel tartozik az adóhatóságnak. 

A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti. Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:

1.  Rákattint az Adó &gt; Közvetett adók &gt; Áfa &gt; Adóhatóságok pontra.
2.  Az Általános gyorslapon Kerekítési képernyő mezőjében kiválasztja a Normál lehetőséget.
3.  A Lekerekítés mezőben ezt adja meg: 1,00.
4.  Amikor az áfa kifizetése esedékes az adóhatóság felé, megnyitja az Adók kiegyenlítése és feladása lapot. (Rákattint az Adó &gt; Bevallások &gt; Áfa &gt; Áfa kiegyenlítése és feladása pontra.)
5.  Az áfakiegyenlítési számlán az adókötelezettség, amely 98.765,43, 98.765-re lesz kerekítve.

Az alábbi táblázat bemutatja, hogyan kerekítjük a 98.765,43 összeget az egyes kerekítési módok használatával az Adóhatóságok lapon, a Kerekítési képernyő mezőjében.

| Kerekítési képernyőopció                | Lekerekítési érték = 0,01 | Lekerekítési érték = 0,10 | Lekerekítési érték = 1,00 | Lekerekítési érték = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normál                              | 98.765,43              | 98.765,40              | 98.765,00              | 98.800,00                |
| Lefelé                            | 98.765,43              | 98.765,40              | 98,765.00              | 98.700,00                |
| Felkerekítés                         | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |
| Saját előny, egy követel egyenleghez | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| Saját előny, egy tartozik egyenleghez  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |

> [!NOTE]                                                                                  
> Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik. 

További információ a következő témakörökben olvasható:
- [Áfa áttekintése](indirect-taxes-overview.md)
- [Áfakifizetés létrehozása](tasks/create-sales-tax-payment.md)
- [Értékesítési tranzakciók létrehozása dokumentumokra](tasks/create-sales-tax-transactions-documents.md)
- [Feladott áfatranzakciók megtekintése](tasks/view-posted-sales-tax-transactions.md)



