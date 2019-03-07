---
title: Részleges szállítói kifizetés kiegyenlítése és az utolsó részlet teljes kiegyenlítése a készpénzfizetési engedmény dátuma előtt
description: Ez a cikk azt az esetet mutatja be, amely során a szállítói számlára vonatkozóan készülnek el a részleges kifizetések és a készpénzfizetési engedmény igénybe van véve.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ada8331e0ddac9fd0aaf8e2c75b6b64ede1d5cd9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "361107"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Részleges szállítói kifizetés kiegyenlítése és az utolsó részlet teljes kiegyenlítése a készpénzfizetési engedmény dátuma előtt

[!include [banner](../includes/banner.md)]

Ez a cikk azt az esetet mutatja be, amely során a szállítói számlára vonatkozóan készülnek el a részleges kifizetések és a készpénzfizetési engedmény igénybe van véve.

A Fabrikam 3064.-es számú szállítótól árut szerez be. A szállító 1 százalékos készpénzfizetési engedményt ad a Fabrikamnak, ha a számlát 14 napon belül fizetik. A számlakat 30 napon belül be kell fizetni. A szállító továbbá engedélyezi a Gyárnak, készpénzfizetési engedményeket a részleges fizetések esetén. A Kiegyenlítési paraméterek a **Kötelezettségek paraméterei** oldalon találhatók. Június 25-én April egy 1000,00 értékű számlát rögzít 3064-es szállító számára.

## <a name="vendor-invoice-on-june-25"></a>Szállítói számla június 25-én
Június 25-én April egy 1.000,00 értékű számlát rögzít és ad fel 3064-es szállító számára. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat   | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg   | Pénznem |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 2015-06-25 | 10010   |                                      | 1000,00                              | -1000,00 | dollár      |

A **Szállítók** oldalon April megnyitja a **Tranzakciók kiegyenlítése** lapot. A **Tranzakciók kiegyenlítése** lapon tekintheti meg a dátumokat és a készpénzfizetési engedmények összegét. A határidő július 25, és egy -10,00 értékű készpénzfizetési engedmény érhető el, ha a számla kifizetése július 9-ig megtörténik.

| Jelölés | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normál            | Inv-10010 | 3064    | 2015-06-25 | 2015/07/25 | 10010   | 1000,00                       | dollár      | 990,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -10,00    |

April rákattint a **Készpénzfizetési engedmény** lapra, hogy megnézze az engedmény összegét.

| Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege | Összeg a tranzakció pénznemében. |
|--------------------|----------------------|--------------------------------|
| 2015/9/7           | 10,00                | 990,00                         |
| 2015/07/25          | 0,00                 | 1000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Részleges kifizetés július 1.-én a Tranzakciók kiegyenlítése lapon
April kifizetési naplót hozhat létre ehhez a fizetéshez, ha megnyitja a **Fizetési napló** lapot a Kötelezettségek modulban. Létrehoz egy új naplót, és rögzít egy sort a 3064-es szállítónak. Anna ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje. April megjelöli a számlát, és a **Kiegyenlítendő összeg** mezőt **-500,00** értékre módosítja. Látható, hogy a **Készpénzfizetési engedmény összege** mező értéke **-10,00** a teljes számála, és az érték az **Alkalmazandó készpénzfizetési engedmény összege** mezőben **-5,05**. Ezért April -505,05 értéket egyenlít ki ebből a számlából.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015/07/25 | 10010   | 1000,00                       | dollár      | -500,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -5,05     |

April pontosan a számla felét szeretné kiegyenlíteni. Ezért megjelöli a számlát, és a **Kiegyenlítendő összeg** mezőt **-495,00** értékre módosítja. Így a teljes kiegyenlített összeg 500,00 lesz. Ez az összeg -5,00 készpénzes engedményt is tartalmaz.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015/07/25 | 10010   | 1000,00                       | dollár      | -495,00          |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -5,00     |

April bezárja a **Tranzakciók kiegyenlítése** oldalt. 495,00 értékű kifizetési sor jön létre a naplóban, majd ezután April feladja a naplót. April a szállítói tranzakciókat a **Szállítói tranzakciók** oldalon tekintheti meg. Azt látja, hogy a számla egyenlege -500,00. Emellett láthat egy 495,00 értékű kifizetést és egy 5,00 értékű készpénzfizetési engedményt is.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Számla          | 2015-06-25 | 10010   |                                      | 1000,00                              | -500,00 | dollár      |
| APP-10010  | Kifizetés          | 2015-1-7  |         | 495,00                               |                                       | 0,00    | dollár      |
| DISC-10010 | Készpénzfizetési engedmény    | 2015-1-7  |         | 5,00                                 |                                       | 0,00    | dollár      |

## <a name="remaining-amount-paid-on-july-8"></a>A fennmaradó összeg kifizetése július 8-án
April kifizeti a 3064-es szállító számlájának fennmaradó részét július 8.-án, ami még beleesik a kedvezményes időszakba. April létrehozza a kifizetési naplót július 8.-án, és a tranzakciót kiegyenlítésre jelöli. Látja, hogy az elszámolandó összeg 495,00. Az érték a **Becsült készpénzfizetési engedmény** mezőben **-5,00**, mert az 5,00 engedményt korábban már érvényesítették

|                         |        |
|-------------------------|--------|
| Megjelölt összesen            | 495,00 |
| Becsült készpénzfizetési engedmény | -5,00  |

A kijelölt tranzakcióval kapcsolatos információk megjelennek a **Nyitott tranzakciók kiegyenlítése** oldal táblázatában.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015-07-25 | 10010   | 1000,00                       | dollár      | 495,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 10,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 5,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 5,00      |

April feladja a kifizetési naplót, és áttekinti a szállítói tranzakciókat a **Szállítói tranzakciók** oldalon. A számla egyenlege ezúttal 0,00, és April két kifizetést és két készpénzfizetési engedményt láthat.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Számla          | 2015-06-25 | 10010   |                                      | 1000,00                              | 0,00    | dollár      |
| APP-10010  |  Kifizetés         | 2015-1-7  |         | 495,00                               |                                       | 0,00    | dollár      |
| DISC-10010 | Készpénzfizetési engedmény    | 2015-1-7  |         | 5,00                                 |                                       | 0,00    | dollár      |
| APP-10011  | Kifizetés          | 2015/8/7  |         | 495,00                               |                                       | 0,00    | dollár      |
| DISC-10011 | Készpénzfizetési engedmény    | 2015-08-07  |         | 5,00                                 |                                       | 0,00    | dollár      |





