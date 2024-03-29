---
title: Forgalmi adókifizetések és kerekítési szabályok
description: Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.
author: kailiang
ms.date: 10/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: kfend
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c24a9850543e9d08ee1726186f433c7cfd26608
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865683"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Forgalmi adókifizetések és kerekítési szabályok

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.

Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak. Ez a művelet az **Áfa** oldalon az Áfa kiegyenlítése és feladása folyamat használatával végezhető el. Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára. A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a **Forgalmi adó** lapon. 

A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.

Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.

## <a name="examples"></a>Példák

Az időszak teljes áfája -98,765.43 követel egyenleget mutat. A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett. Emiatt a jogi személy pénzzel tartozik az adóhatóságnak. 

A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti. Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:

1. Kattintson az **Adó** > **Közvetett adók** > **Áfa** > **Adóhatóságok** pontra.
2. Az **Általános** gyorslapon a **Kerekítési képernyő** mezőjében válassza a **Normál** lehetőséget.
3. A **Lekerekítés** mezőben ezt adja meg: 1,00.
4. Amikor az áfa kifizetése esedékes az adóhatóság felé, nyissa meg az **Adó** > **Nyilatkozatok** > **Áfa** > **Áfa kiegyenlítése és feladása** lehetőséget. Az áfakiegyenlítési számlán látható az adókötelezettség, amely **98 765,43** és **98 765**-re lesz kerekítve.

Az alábbi táblázat bemutatja, hogyan kerekítjük a 98 765,43 összeget az egyes kerekítési módok használatával az **Adóhatóságok lapon**, a **Kerekítési képernyő** mezőjében.

> [!NOTE]                                                                                  
> Ha a kerekítési érték 0,00, akkor:
>
> - Normál kerekítés esetén a kerekítési mód ugyanaz, mint a **Lekerekítés = 0,01** esetében.
> - A **Kerekítési képernyő beállításai**, **Lefelé**, **Felkerekítés** és **Saját előny** esetében a viselkedés ugyanaz, mint a **Lekerekítés = 1,00** esetében.

| Kerekítési képernyőopció                | Lekerekítési érték = 0,01 | Lekerekítési érték = 0,10 | Lekerekítési érték = 1,00 | Lekerekítési érték = 100,00 | Lekerekítési érték = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normál                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| Lefelé                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Felkerekítés                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| Saját előny, egy követel egyenleghez | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Saját előny, egy tartozik egyenleghez  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Normál kerekítés és kerekítési pontosság 0,01

```<table>
  <tr>
    <td>Rounding
    </td>
    <td>Calculation process
    </td>
  </tr>
    <tr>
    <td>round(1.015, 0.01) = 1.02
    </td>
    <td>
      <ol>
        <li>round(1.015 / 0.01, 0) = round(101.5, 0) = 102
        </li>
        <li>102 * 0.01 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.014, 0.01) = 1.01
    </td>
    <td> <ol>
        <li>round(1.014 / 0.01, 0) = round(101.4, 0) = 101
        </li>
        <li>101 * 0.01 = 1.01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.011, 0.02) = 1.02
    </td>
    <td> <ol>
        <li>round(1.011 / 0.02, 0) = round(50.55, 0) = 51
        </li>
        <li>51 * 0.02 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.009, 0.02) = 1.00
    </td>
    <td> <ol>
        <li>round(1.009 / 0.02, 0) = round(50.45, 0) = 50
        </li>
        <li>50 * 0.02 = 1.00
        </li>
      </ol>
    </td>
  </tr>
</table>
```

> [!NOTE]                                                                                  
> Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik. 

További információ a következő témakörökben olvasható:
- [Áfa áttekintése](indirect-taxes-overview.md)
- [Áfakifizetés létrehozása](tasks/create-sales-tax-payment.md)
- [Áfatranzakciók létrehozása dokumentumokra](tasks/create-sales-tax-transactions-documents.md)
- [Feladott áfatranzakciók megtekintése](tasks/view-posted-sales-tax-transactions.md)
- [kerekítés függvény](/previous-versions/dynamics/ax-2012/reference/aa850656(v=ax.60))




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
