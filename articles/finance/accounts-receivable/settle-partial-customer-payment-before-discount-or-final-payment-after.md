---
title: Részleges vevői kifizetés rendezése az engedmény dátuma előtt, végső fizetés az engedmény bevezetésének dátuma után
description: Ez a cikk fizetéskiegyenlítések számlákra és vevőkre gyakorolt hatását taglalja. Az eset nem a főkönyvre, hanem az analitikus naplóra gyakorolt hatásokra összpontosít.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f6b4527a9f176857e0cc6ba4665688dc8721ac1
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780227"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>Részleges vevői kifizetés rendezése az engedmény dátuma előtt, végső fizetés az engedmény bevezetésének dátuma után

[!include [banner](../includes/banner.md)]

Ez a cikk fizetéskiegyenlítések számlákra és vevőkre gyakorolt hatását taglalja. Az eset nem a főkönyvre, hanem az analitikus naplóra gyakorolt hatásokra összpontosít.

A FabriKam a 4027.-es számú vevőnek árut értékesít. A Gyár 1 százalékos készpénzfizetési engedményt ajánl, ha a számla 14 napon belül befizetésre kerül. A számlakat 30 napon belül be kell fizetni. A Fabrikam emellett a részleges kifizetésekra is nyújt készpénzfizetési engedményt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="invoice"></a>Számla
Június 25-én Arnie egy 1.000,00 értékű számlát rögzít és ad fel 4027-es vevő számára. Ezt a számlát Arnie a **Tranzakciók** gombra kattintva a **Vevők** oldalon tekintheti meg.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Számla          | 2020/25/6 | 10020   | 1,000.00                             |                                       | 1,000.00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Részleges kifizetés a készpénzfizetési engedmény dátuma előtt
Július 2-án a 4027.-es számú vevő elvégzi a 297.00 értékű részfizetést a számlához. A fizetés jogosult készpénzfizetési kedvezményre, mivel a FabriKam készpénzfizetési kedvezményt kínál a részfizetésekre, valamint a részfizetés a készpénzfizetési kedvezmény előtt történt. Emiatt a 4027.-es számú vevő 3.00 értékű készpénzfizetési kedvezményben részesül. Anna a Kifizetési naplóba rögzíti a 4027.-es számú vevő fizetését. Arnie ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Kiválasztva | Normál            | FTI-10020 | 4027    | 2020/25/6 | 2020/25/7 | 10020   | 1,000.00                             | USD      | 297.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Ha nem módosítja a **Kiegyenlítendő összeg** értékét 297.00-re, a **Készpénzfizetési engedmény összege** eltérő lesz. A 3.00 érték készpénzfizetési engedményként jelenik meg a fizetés feladása alkalmával, mert a kiegyenlítés automatikusan módosítja a **Kiegyenlítendő összeg** értékét.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 10,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 3,00      |

Anna feladja ezt a fizetést. A számla egyenlege jelenleg 700,00. A következő tranzakciók láthatóak a vevő számára.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Számla          | 2020/25/6 | 10020   | 1,000.00                             |                                       | 700.00  | USD      |
| ARP-10020  |  Kifizetés         | 2020/1/7  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |  Készpénzfizetési engedmény   | 2020/1/7  |         |                                      | 3.00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>A készpénzfizetési engedmény dátuma után fennmaradó fizetés.
Július 11-én, a kedvezményes időszak után, a 4027.-es számú vevő kifizeti a számla maradék részét. A **Tranzakciók kiegyenlítése** lapon az engedmény összege nem jelenik meg a **Becsült készpénzfizetési engedmény** mezőben, valamint a **Készpénzfizetési engedmény összege** mező értéke **0,00**. Ha a 4027.-es számú vevő kifizeti a hátralévő 700.00 értéket, további kedvezményt nem kap.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Kiválasztva | Normál            | FTI-10020 | 4027    | 2020/25/6 | 2020/25/7 | 10020   | 700.00                               | USD      | 700.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 0,00      |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 3,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 0,00      |

Ha Anna módosítja a **Készpénzfizetési engedmény használata** mezőt **Mindig** értékűre, a **Részleges kifizetések készpénzfizetési engedményeinek számítása** beállítás érvényét veszti, és a készpénzfizetési engedményt veszi figyelembe. A kifizetés összege 693.00 értékre változik, és a fennmaradó 7.00 érték a készpénzfizetési összeg.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|---------------|---------------------|----------|------------------|
| Kiválasztva | Mindig            | FTI-10020 | 4027    | 2020/25/6 | 2020/25/7 | 10020   | 700.00        |                        | USD      | 693.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 7.00      |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | 3,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 7:00      |

Arnie a **Készpénzfizetési engedmény használata** mezőt visszaállítja **Normál** értékre, mert nem engedi, hogy a vevő a fennmaradó, 7,00 értékű készpénzfizetési engedményt igénybe vegye. Anna ezután feladja ezt a fizetést. Amikor Arnie megnyitja a **Vevőtranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Két kifizetés létezik: Az egyik kifizetés 297.00 értékű és tartozik hozzá egy 3.00 értékű készpénzfizetési kedvezmény. A másik kifizetés 700.00 értékű.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Számla          | 2020/25/6 | 10020   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 2020/1/7  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |                  | 2020/1/7  |         |                                      | 3.00                                  | 0,00    | USD      |
| ARP-10021  |                  | 2020/11/7 |         |                                      | 700.00                                | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
