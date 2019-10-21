---
title: Forgalmi adókifizetések és kerekítési szabályok
description: Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186325"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Forgalmi adókifizetések és kerekítési szabályok

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.

Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak. Ez a Forgalmi adó oldalon a forgalmi adó rendezése és feladása folyamat használatával végezhető el. Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára. A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon. 

A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.

Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.

## <a name="examples"></a>Példák

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


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a>Nincs kerekítés, mivel a kerekítés 0,00

ekerekítés(1,0151, 0,00) = 1,0151 kerekítés(1,0149, 0,00) = 1,0149

### <a name="normal-round-and-round-precision-is-001"></a>Normál kerekítés és kerekítési pontosság 0,01

<table>
  <tr>
    <td>Kerekítés
    </td>
    <td>Számítási folyamat
    </td>
  </tr>
    <tr>
    <td>kerekítés(1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>kerekítés(1,015 / 0,01, 0) = kerekítés(101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>kerekítés(1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>kerekítés(1,014 / 0,01, 0) = kerekítés(101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>kerekítés(1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>kerekítés(1,011 / 0,02, 0) = kerekítés(50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>kerekítés(1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>kerekítés(1,009 / 0,02, 0) = kerekítés(50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik. 

További információ a következő témakörökben olvasható:
- [Áfa áttekintése](indirect-taxes-overview.md)
- [Áfakifizetés létrehozása](tasks/create-sales-tax-payment.md)
- [Értékesítési tranzakciók létrehozása dokumentumokra](tasks/create-sales-tax-transactions-documents.md)
- [Feladott áfatranzakciók megtekintése](tasks/view-posted-sales-tax-transactions.md)
- [kerekítés függvény](https://msdn.microsoft.com/library/aa850656.aspx)


