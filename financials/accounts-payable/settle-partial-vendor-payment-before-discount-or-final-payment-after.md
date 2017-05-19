---
title: "A vevő az ár egy részét az engedmény dátuma előtt rendezte, azonban a végső fizetés az engedmény bevezetésének dátuma után történik."
description: "Ez a cikk egy olyan esetet mutat be, ahol több részfizetés is történt: néhány a készpénzfizetési engedmény időszakán belül, a többi pedig a készpénzfizetési engedmény időszakán kívül."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c7ab943d368c82e7d6c586ec5105210a928e2d31
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="settle-a-partial-vendor-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>A vevő az ár egy részét az engedmény dátuma előtt rendezte, azonban a végső fizetés az engedmény bevezetésének dátuma után történik.

[!include[banner](../includes/banner.md)]


Ez a cikk egy olyan esetet mutat be, ahol több részfizetés is történt: néhány a készpénzfizetési engedmény időszakán belül, a többi pedig a készpénzfizetési engedmény időszakán kívül.

A Gyár 3057.-es számú szállítótól árut szerez be. A Gyár 1 százalékos készpénzfizetési engedményt kap, ha a számla 14 napon belül befizetésre kerül. A számlakat 30 napon belül be kell fizetni. A szállító továbbá engedélyezi a Gyárnak, készpénzfizetési engedményeket a részleges fizetések esetén. A Kiegyenlítési paraméterek a **Kötelezettségek paraméterei** oldalon találhatók.

## <a name="invoice-on-june-25"></a>Számla június 25-én
Június 25-én April egy 1.000,00 értékű számlát rögzít és ad fel 3057-es szállító számára. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg   | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Számla          | 2015-06-25 | 10020   |                                      | 1000,00                              | -1 000,00 | dollár      |

## <a name="partial-payment-on-july-2"></a>Részleges kifizetés július 2-án
Július 2-án April szeretne kiegyenlíteni a számlájából 300,00 összegű részt. A kifizetés jogosult egy engedményre, mert a Gyár elfogad engedményeket a részleges kifizetéseken. Ezért April 297,00-et fizet és kap 3,00 engedményt. Létrehoz egy kifizetési naplót és rögzít egy sort a 3057-es szállítónak. Anna ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | Inv-10020 | 3057    | 2015-06-25 | 2015-07-25 | 10020   | -1 000,00                      | dollár      | -297,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -3,00     |

April ezután feladja ezt a fizetést. A számla egyenlege jelenleg 700,00. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2015-06-25 | 10020   |                                      | 1000,00                              | -700,00 | dollár      |
| APP-10020  | Kifizetés          | 2015-01-07  |         | 297,00                               |                                       | 0,00    | dollár      |
| DISC-10020 | Készpénzfizetési engedmény    | 2015-01-07  |         | 3,00                                 |                                       | 0,00    | dollár      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>A fennmaradó fizetés június 15-én, a készpénzfizetési engedmény használata = normál
April kifizeti a számla fennmaradó részét július 15-én, ami a kedvezményes időszak után van. A **Nyíl tranzakciók kiegyenlítése** lapon az engedmény összege nem jelenik meg a **Becsült készpénzfizetési engedmény**mezőben, valamint a **Készpénzfizetési engedmény összege** mező értéke **0,00**. Amikor April kifizeti a maradék 700,00 egységet nem kap további engedményt.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | Inv-10020 | 3057    | 2015-06-25 | 2015-07-25 | 10020   | -700,00                        | dollár      | -700,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. April megtekintheti, hogy már kapott 3,00 engedményt.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 0,00      |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | -3,00     |
| Alkalmazandó készpénzfizetési engedmény összege | 0,00      |

April ezután feladja ezt a fizetést. Amikor megnyitja a **Szállítótranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Azt is látja, hogy van két kifizetés. Az egyik kifizetés 297,00 értékű és tartozik hozzá egy 3,00 értékű készpénzfizetési kedvezmény. A másik kifizetés 700,00 értékű.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2015-06-25 | 10020   |                                      | 1000,00                              | 0,00    | dollár      |
| APP-10020  | Kifizetés          | 2015-01-07  |         | 297,00                               |                                       | 0,00    | dollár      |
| DISC-10020 | Készpénzfizetési engedmény    | 2015-01-07  |         | 3,00                                 |                                       | 0,00    | dollár      |
| APP-10021  | Kifizetés          | 2015-07-15 |         | 700,00                               |                                       | 0,00    | dollár      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>A fennmaradó fizetés július 15-én, a készpénzfizetési engedmény használata = mindig
Ha a szállító lehetővé teszi, hogy April a megkapja az engedményt, annak ellenére, hogy a készpénzfizetési engedmény dátuma után fizet, akkor meg tudja változtatni az értéket a **Készpénzfizetési engedmény használata** mezőben **Mindig** értékre. A **Részleges kifizetések készpénzfizetési engedményeinek számítása** beállítás felülíródik és érvényesül a kedvezmény. A kifizetés összege 693,00, a kedvezmény pedig a fennmaradó 7,00.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Kijelölve | Mindig            | Inv-10020 | 3057    | 2015-06-25 | 2015-07-25 | 10020   | 700,00                               |                                       | dollár      | -693,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 7:00      |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | -3,00     |
| Alkalmazandó készpénzfizetési engedmény összege | -7,00     |

April ezután feladja ezt a fizetést. Amikor megnyitja a **Szállítótranzakciók** lapot, azt látja, hogy a számla egyenlege 0,00 érték. Azt is látja, hogy van két kifizetés. Az egyik kifizetés 297,00 értékű és tartozik hozzá egy 3,00 értékű készpénzfizetési kedvezmény. A másik kifizetés 693,00 értékű és 7,00 értékű kedvezménye van.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Számla          | 2015-06-25 | 10020   |                                      | 1000,00                              | 0,00    | dollár      |
| APP-10020  | Kifizetés          | 2015-01-07  |         | 297,00                               |                                       | 0,00    | dollár      |
| DISC-10020 | Készpénzfizetési engedmény    | 2015-01-07  |         | 3,00                                 |                                       | 0,00    | dollár      |
| APP-10021  | Kifizetés          | 2015-07-15 |         | 693,00                               |                                       | 0,00    | dollár      |
| DISC-10021 | Készpénzfizetési engedmény    | 2015-07-15 |         | 7:00                                 |                                       | 0,00    | dollár      |






