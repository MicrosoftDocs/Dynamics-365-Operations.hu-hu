---
title: Vevői kifizetés egy részének rendezése, amely több kedvezményes időszakkal rendelkezik
description: Ez a cikk ismerteti, hogy a részleges vevői kifizetések hogyan kerülnek kiegyenlítésre több engedményes időszak esetén.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62defda8831d2915050fc6822f60a905f067fe88
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778439"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Vevői kifizetés egy részének rendezése, amely több kedvezményes időszakkal rendelkezik

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogy a részleges vevői kifizetések hogyan kerülnek kiegyenlítésre több engedményes időszak esetén.

A Fabrikam 4031. számú vevőjének két készpénzfizetési engedményes időszakot is kínál. A vevő 2 százalékos készpénzfizetési engedményt kap, ha a számlát öt napon belül kifizeti, és 1 százalékot, ha a számlát 14 napon belül kifizeti. A Fabrikam emellett a részleges kifizetésekra is nyújt készpénzfizetési engedményt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="invoice"></a>Számla
Június 25-én Arnie egy 1.000,00 értékű számlát rögzít és ad fel 4031-es vevő számára. Amikor Arnie megnézi a számlára vonatkozó készpénzfizetési engedményeket, azt látja, hogy a 4031-es vevő 20,00 engedményt kap, ha június 30-ig fizet. Ha a számla teljes összegét kifizeti július 9.-ig, akkor 10,00 értékű engedményt kap.

| Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege | Összeg a tranzakció pénznemében. |
|--------------------|----------------------|--------------------------------|
| 2020.06.30.          | 20.00                | 980.00                         |
| 2020/9/7           | 10,00                | 990.00                         |
| 2020/25/7          | 0,00                 | 1,000.00                       |

Arnie megtekintheti ezt a tranzakciót a **Vevői tranzakciók** oldalon.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Számla          | 2020/25/6 | 10030   | 1,000.00                             |                                       | 1,000.00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Részleges kifizetés a készpénzfizetési engedmény dátuma előtt
Június 28.-án a 4031. számú vevő 294,00 értékű részfizetést teljesít. Mivel június 28. az első készpénzfizetési engedményidőszakon belül van, a vevő 6,00 engedményt vesz igénybe. A **Tranzakciók kiegyenlítése** lapon a **Készpénzfizetési engedmény összege** mező értéke 20,00, és az **Alkalmazandó készpénzfizetési engedmény összege** mező értéke 6,00.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva | Normál            | FTI-10030 | 4031    | 2020/25/6 | 2020/25/7 | 10030   | 1,000.00                       | USD      | 294,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Ha nem módosítja a **Kiegyenlítendő összeg** értékét **294.00**-re, a **Készpénzfizetési engedmény összege** eltérő lesz. A 6,00 érték azonban készpénzfizetési engedményként jelenik meg a fizetés feladása alkalmával, mert a kiegyenlítés automatikusan módosítja a **Kiegyenlítendő összeg** értékét.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020.06.30. |
| Készpénzfizetési engedmény összege         | 20.00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 6,00      |

Miután Arnie feladta a kifizetést, a számla egyenlege 700,00 lesz.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Részleges kifizetés a második készpénzfizetési engedmény dátuma előtt
Július 8.-án a vevő kifizeti a fennmaradó számlaösszeget. Mivel ezt kifizetést az engedmény második időszakában egyenlítik ki, ezért 7,00 értékű (1 százalékos) engedmény vonatkozik rá.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------|-----------------------|----------|------------------|
| Kiválasztva | Normál            | FTI-10030 | 4031    | 2020/25/6 | 2020/25/7 | 10030   | 700.00       |            | USD      | 693.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 30.00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 6,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 7:00      |

A számla egyenlege ekkor 0,00. Arnie megtekintheti ezt az információt a **Vevői tranzakciók** oldalon.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Számla          | 2020/25/6 | 10030   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10030  |  Kifizetés         | 2020/28/6 |         |                                      | 294,00                                | 0,00    | USD      |
| DISC-10030 |  Készpénzfizetési engedmény   | 2020/28/6 |         |                                      | 6,00                                  | 0,00    | USD      |
| ARP-10031  |  Kifizetés         | 2020/8/7  |         |                                      | 693.00                                | 0,00    | USD      |
| DISC-1031  |  Készpénzfizetési engedmény   | 2020/8/7  |         |                                      | 7.00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
