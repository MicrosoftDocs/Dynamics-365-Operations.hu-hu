---
title: A vevő az ár egy részét az engedmény dátuma előtt rendezte, azonban a végső fizetés az engedmény bevezetésének dátuma után történik.
description: Ez a cikk fizetéskiegyenlítések számlákra és vevőkre gyakorolt hatását taglalja. Az eset nem a főkönyvre, hanem az analitikus naplóra gyakorolt hatásokra összpontosít.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a71d0931445f3501f1b74f26c5eef583ab598b3c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843097"
---
# <a name="settle-a-partial-customer-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>A vevő az ár egy részét az engedmény dátuma előtt rendezte, azonban a végső fizetés az engedmény bevezetésének dátuma után történik.

[!include [banner](../includes/banner.md)]

Ez a cikk fizetéskiegyenlítések számlákra és vevőkre gyakorolt hatását taglalja. Az eset nem a főkönyvre, hanem az analitikus naplóra gyakorolt hatásokra összpontosít.

A FabriKam a 4027.-es számú vevőnek árut értékesít. A Gyár 1 százalékos készpénzfizetési engedményt ajánl, ha a számla 14 napon belül befizetésre kerül. A számlakat 30 napon belül be kell fizetni. A Fabrikam emellett a részleges kifizetésekra is nyújt készpénzfizetési engedményt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="invoice"></a>Számla
Június 25-én Arnie egy 1.000,00 értékű számlát rögzít és ad fel 4027-es vevő számára. Ezt a számlát Arnie a **Tranzakciók** gombra kattintva a **Vevők** oldalon tekintheti meg.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Számla          | 2015-06-25 | 10020   | 1000,00                             |                                       | 1000,00 | dollár      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Részleges kifizetés a készpénzfizetési engedmény dátuma előtt
Július 2-án a 4027.-es számú vevő elvégzi a 297.00 értékű részfizetést a számlához. A fizetés jogosult készpénzfizetési kedvezményre, mivel a FabriKam készpénzfizetési kedvezményt kínál a részfizetésekre, valamint a részfizetés a készpénzfizetési kedvezmény előtt történt. Emiatt a 4027.-es számú vevő 3.00 értékű készpénzfizetési kedvezményben részesül. Anna a Kifizetési naplóba rögzíti a 4027.-es számú vevő fizetését. Anna ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10020 | 4027    | 2015-06-25 | 2015-07-25 | 10020   | 1000,00                             | dollár      | 297.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Ha nem módosítja a **Kiegyenlítendő összeg** értékét 297.00-re, a **Készpénzfizetési engedmény összege** eltérő lesz. A 3.00 érték készpénzfizetési engedményként jelenik meg a fizetés feladása alkalmával, mert a kiegyenlítés automatikusan módosítja a **Kiegyenlítendő összeg** értékét.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 1000     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 3,00      |

Anna feladja ezt a fizetést. A számla egyenlege jelenleg 700,00. A következő tranzakciók láthatóak a vevő számára.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Számla          | 2015-06-25 | 10020   | 1000,00                             |                                       | 700.00  | dollár      |
| ARP-10020  |  Kifizetés         | 2015-1-7  |         |                                      | 297.00                                | 0,00    | dollár      |
| DISC-10020 |  Készpénzfizetési engedmény   | 2015-1-7  |         |                                      | 3,00                                  | 0,00    | dollár      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>A készpénzfizetési engedmény dátuma után fennmaradó fizetés.
Július 11-én, a kedvezményes időszak után, a 4027.-es számú vevő kifizeti a számla maradék részét. A **Tranzakciók kiegyenlítése** lapon az engedmény összege nem jelenik meg a **Becsült készpénzfizetési engedmény** mezőben, valamint a **Készpénzfizetési engedmény összege** mező értéke **0,00**. Ha a 4027.-es számú vevő kifizeti a hátralévő 700.00 értéket, további kedvezményt nem kap.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10020 | 4027    | 2015-06-25 | 2015-07-25 | 10020   | 700.00                               | dollár      | 700.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 0,00      |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 3,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 0,00      |

Ha Anna módosítja a **Készpénzfizetési engedmény használata** mezőt **Mindig**értékűre, a **Részleges kifizetések készpénzfizetési engedményeinek számítása** beállítás érvényét veszti, és a készpénzfizetési engedményt veszi figyelembe. A kifizetés összege 693.00 értékre változik, és a fennmaradó 7.00 érték a készpénzfizetési összeg.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Kijelölve | Mindig            | FTI-10020 | 4027    | 2015-06-25 | 2015-07-25 | 10020   | 700.00                               |                                       | dollár      | 693.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 7:00      |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | 3,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 7:00      |

Anna a **Készpénzfizetési engedmény használata** mezőt visszaállítja **Normál**értékre, mert nem engedi, hogy a vevő a fennmaradó, 7.00 értékű készpénzfizetési engedményt igénybe vegye. Anna ezután feladja ezt a fizetést. Amikor Anna megnyitja a**Vevőtranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Azt is látja, hogy van két kifizetés. Az egyik kifizetés 297.00 értékű és tartozik hozzá egy 3.00 értékű készpénzfizetési kedvezmény. A másik kifizetés 700.00 értékű.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Számla          | 2015-06-25 | 10020   | 1000,00                             |                                       | 0,00    | dollár      |
| ARP-10020  |                  | 2015-1-7  |         |                                      | 297.00                                | 0,00    | dollár      |
| DISC-10020 |                  | 2015-1-7  |         |                                      | 3,00                                  | 0,00    | dollár      |
| ARP-10021  |                  | 2015-11-7 |         |                                      | 700.00                                | 0,00    | dollár      |





