---
title: Teljesösszeg- és intervallumszámítási opciók áfakódokhoz
description: Ez a témakör bemutatja a Számítási mód áfakódokra vonatkozó beállításait, valamint a forgalmi adó számítását intervallumokra és teljes összegekre.
author: kailiang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f06c92f2151f54a7d9b684b9687b786d1e4cd7a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727454"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Teljesösszeg- és intervallumszámítási opciók áfakódokhoz

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a **Számítási mód** mező áfakódokra vonatkozó beállításait, valamint a forgalmi adó számítását intervallumokra és teljes összegekre.

Beállíthatja, hogy az áfakód egy teljes összeg, vagy egy időszakhoz tartozó összeget alapján alapján legyen kiszámítva. Az **Áfakódok** lapon használja a **Számítási mód** mezőt a **Számítás** gyorslapon az áfakód számítási módjának kiválasztásához.
- Teljes összeg – Az áfakulcs a teljes adózó összegre vonatkozik.
- Intervallum – Az adóalap részekre oszlik, és mindegyik rész egy tartományba esik, amelynek saját áfakulcsa van. Az egyes részek áfájának számítása az adott részt tartalmazó intervallumra vonatkozó áfakulcs alapján történik. Az áfa értéke az egyes intervallumokra kiszámított áfák összegével egyenlő.
  > [!NOTE]                                                                                                                              
  > Az intervallum lehetőség csak akkor érhető el, ha kiválasztja a Sort a Számítási mód mezőjében a Főkönyvi paraméterek oldalon a Forgalmi adó területen. 

Az intervallumok beállítása a Forgalmi adó kódlapon történik, úgy, hogy adókulcsonként Minimális és Maximális korlátösszegeket adunk meg. Az adóköteles összegekre számítandó áfák intervallumainak – a kiválasztott számítási módszertől függetlenül – a következő szabályoknak kell megfelelniük:
-   Az első intervallumnak 0 kell, hogy legyen a Minimális határértéke.
-   Az utolsó intervallumnak nulla Maximális korláttal kell rendelkeznie, ami a végtelent jelenti.
-   A Maximális korlát egy intervallum esetében a következő intervallum Minimális korlátja kell, hogy legyen.

Ha egy összeg megegyezik egy intervallum Maximális határával, ezáltal a következő intervallum Minimális határával is, akkor az első intervallum áfakulcsa vonatkozik az összegre. Ha egy összeg kívül esik a felső és alsó határok által megadott intervallumokon, akkor a program nullás áfakulcsot alkalmaz.

## <a name="example-whole-amount-method-of-calculation"></a>Példa: Teljes összegű számítási mód
Az Áfakód értékek kódlapon a következő intervallumokban vannak beállítva az áfakulcsok:

| Minimumhatár     | Maximum határ     | Áfakulcs     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Az áfa összegét az egész adóalapra kiszámoljuk.

| Adóalap (ár) | Számítás    | Forgalmi adó |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | 10,50     |
| 50,00                  | 50,00 \* 0,30  | 1500     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a> Példa: Intervallum számítási mód
Az Értékek oldalon az áfakulcsok a következő intervallumokra vannak beállítva:

| Minimumhatár     | Maximum határ     | Áfakulcs     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Az áfa értéke az egyes intervallumokra kiszámított áfák összegével egyenlő.

| Adóalap (ár) | Számítás                                                               | Forgalmi adó |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | 10,50     |
| 50,00                  | 50,00 \* 0,30                                                             | 1500     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45.50     |



További tájékoztatás: [Az áfaérték a Számítás alapja és a Számítási módszerek alapján](marginal-base-field.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
