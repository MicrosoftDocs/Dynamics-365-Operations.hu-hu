---
title: "Részleges szállítói kifizetés és végső kifizetés teljes kiegyenlítése előtt az engedmény dátumát"
description: "Ez a cikk azt az esetet mutatja be, amely során a szállítói számlára vonatkozóan készülnek el a részleges kifizetések és a készpénzfizetési engedmény igénybe van véve."
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
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 6cd87dc1b34d1d689d5417359e1ec3a34d53afb4
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Részleges szállítói kifizetés és végső kifizetés teljes kiegyenlítése előtt az engedmény dátumát

Ez a cikk azt az esetet mutatja be, amely során a szállítói számlára vonatkozóan készülnek el a részleges kifizetések és a készpénzfizetési engedmény igénybe van véve.

A Fabrikam vásárol árut szállító 3064. A szállító nyújt a Fabrikam 1 százalékos készpénzfizetési engedményt, ha a számla kifizetése 14 napon belül. A számlakat 30 napon belül be kell fizetni. A szállító továbbá engedélyezi a Gyárnak, készpénzfizetési engedményeket a részleges fizetések esetén. A kiegyenlítés paraméterek találhatók a **kötelezettségek paramétereinek** oldalon. Június 25-én April egy 1000,00 értékű számlát rögzít 3064-es szállító számára.

## <a name="vendor-invoice-on-june-25"></a>Szállítói számla június 25-én
Június 25-én április belép, és 1 000,00 3064 szállítói számlát elkönyveli. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

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
April kifizetési naplót hozhat létre ehhez a fizetéshez, ha megnyitja a **Fizetési napló** lapot a Kötelezettségek modulban. Ő hozzon létre egy új naplót, és egy sor megadja a szállító 3064. Ő majd megnyitja a **tranzakciók kiegyenlítése** oldalon, így ő megjelölheti, hogy a számla kiegyenlítésre. April megjelöli a számlát, és a **Kiegyenlítendő összeg** mezőt **-500,00** értékre módosítja. Látható, hogy a **Készpénzfizetési engedmény összege** mező értéke **-10,00** a teljes számála, és az érték az **Alkalmazandó készpénzfizetési engedmény összege** mezőben **-5,05**. Ezért April -505,05 értéket egyenlít ki ebből a számlából.

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

April bezárja a **Tranzakciók kiegyenlítése** oldalt. 495,00 értékű kifizetési sor jön létre a naplóban, majd ezután April feladja a naplót. Április át tudja tekinteni a szállítói tranzakciók a **szállítói tranzakciók** oldalon. Azt látja, hogy a számla egyenlege a-500.00. Emellett láthat egy 495,00 értékű kifizetést és egy 5,00 értékű készpénzfizetési engedményt is.

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




