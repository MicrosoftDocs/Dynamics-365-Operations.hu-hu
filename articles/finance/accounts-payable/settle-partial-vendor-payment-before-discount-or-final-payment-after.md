---
title: Részleges vevői kifizetés rendezése az engedmény dátuma előtt és végső fizetés az engedmény bevezetésének dátuma után
description: 'Ez a cikk egy olyan esetet mutat be, ahol több részfizetés is történt: néhány a készpénzfizetési engedmény időszakán belül, a többi pedig a készpénzfizetési engedmény időszakán kívül.'
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 828c82d88bef1d942af1219505af591d27043fa5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780239"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Részleges vevői kifizetés rendezése az engedmény dátuma előtt és végső fizetés az engedmény bevezetésének dátuma után

[!include [banner](../includes/banner.md)]

Ez a cikk egy olyan esetet mutat be, ahol több részfizetés is történt: néhány a készpénzfizetési engedmény időszakán belül, a többi pedig a készpénzfizetési engedmény időszakán kívül.

A Gyár 3057.-es számú szállítótól árut szerez be. A Gyár 1 százalékos készpénzfizetési engedményt kap, ha a számla 14 napon belül befizetésre kerül. A számlakat 30 napon belül be kell fizetni. A szállító továbbá engedélyezi a Gyárnak, készpénzfizetési engedményeket a részleges fizetések esetén. A Kiegyenlítési paraméterek a **Kötelezettségek paraméterei** oldalon találhatók.

## <a name="invoice-on-june-25"></a>Számla június 25-én
Június 25-én April egy 1.000,00 értékű számlát rögzít és ad fel 3057-es szállító számára. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg   | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Számla          | 2020/25/6 | 10020   |                                      | 1,000.00                              | -1 000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Részleges kifizetés július 2-án
Július 2-án April szeretne kiegyenlíteni a számlájából 300,00 összegű részt. A kifizetés jogosult egy engedményre, mert a Gyár elfogad engedményeket a részleges kifizetéseken. Ezért April 297,00-et fizet és kap 3,00 engedményt. Létrehoz egy kifizetési naplót és rögzít egy sort a 3057-es szállítónak. Anna ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva | Normál            | Inv-10020 | 3057    | 2020/25/6 | 2020/25/7 | 10020   | -1 000,00                      | USD      | -297,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -3,00     |

April ezután feladja ezt a fizetést. A számla egyenlege jelenleg 700,00. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2020/25/6 | 10020   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10020  | Kifizetés          | 2020/1/7  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Készpénzfizetési engedmény    | 2020/1/7  |         | 3.00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>A fennmaradó fizetés június 15-én, a készpénzfizetési engedmény használata = normál
April kifizeti a számla fennmaradó részét július 15-én, ami a kedvezményes időszak után van. A **Nyíl tranzakciók kiegyenlítése** lapon az engedmény összege nem jelenik meg a **Becsült készpénzfizetési engedmény** mezőben, valamint a **Készpénzfizetési engedmény összege** mező értéke **0,00**. Amikor April kifizeti a maradék 700,00 egységet nem kap további engedményt.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva | Normál            | Inv-10020 | 3057    | 2020/25/6 | 2020/25/7 | 10020   | -700,00                        | USD      | -700,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. April megtekintheti, hogy már kapott 3,00 engedményt.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 0,00      |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | -3,00     |
| Alkalmazandó készpénzfizetési engedmény összege | 0,00      |

April ezután feladja ezt a fizetést. Amikor megnyitja a **Szállítótranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Azt is látja, hogy van két kifizetés. Az egyik kifizetés 297,00 értékű és tartozik hozzá egy 3,00 értékű készpénzfizetési kedvezmény. A másik kifizetés 700,00 értékű.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2020/25/6 | 10020   |                                      | 1,000.00                              | 0,00    | USD      |
| APP-10020  | Kifizetés          | 2020/1/7  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Készpénzfizetési engedmény    | 2020/1/7  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Kifizetés          | 2020/15/7 |         | 700.00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>A fennmaradó fizetés július 15-én, a készpénzfizetési engedmény használata = mindig
Ha a szállító lehetővé teszi, hogy April a megkapja az engedményt, annak ellenére, hogy a készpénzfizetési engedmény dátuma után fizet, akkor meg tudja változtatni az értéket a **Készpénzfizetési engedmény használata** mezőben **Mindig** értékre. A **Részleges kifizetések készpénzfizetési engedményeinek számítása** beállítás felülíródik és érvényesül a kedvezmény. A kifizetés összege 693,00, a kedvezmény pedig a fennmaradó 7,00.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|----------|------|------|-----------|-----------|---------|-----------------------|---------------------------------------|----------|------------------|
| Kiválasztva | Mindig            | Inv-10020 | 3057    | 2020/25/6 | 2020/25/7 | 10020   | 700.00                   |                   | USD      | -693,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/09/7 |
| Készpénzfizetési engedmény összege         | 7.00      |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | -3,00     |
| Alkalmazandó készpénzfizetési engedmény összege | -7,00     |

April ezután feladja ezt a fizetést. Amikor megnyitja a **Szállítótranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Azt is látja, hogy van két kifizetés. Az egyik kifizetés 297,00 értékű és tartozik hozzá egy 3,00 értékű készpénzfizetési kedvezmény. A másik kifizetés 693,00 értékű és 7,00 értékű kedvezménye van.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2020/25/6 | 10020   |                                      | 1,000.00                              | 0,00    | USD      |
| APP-10020  | Kifizetés          | 2020/1/7  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Készpénzfizetési engedmény    | 2020/1/7  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Kifizetés          | 2020/15/7 |         | 693.00                               |                                       | 0,00    | USD      |
| DISC-10021 | Készpénzfizetési engedmény    | 2020/15/7 |         | 7.00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
