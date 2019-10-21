---
title: Részleges vevői kifizetés kiegyenlítése és az utolsó részlet teljes kiegyenlítése a készpénzfizetési engedmény dátuma előtt
description: Ez a cikk olyan eseteket mutat be, amelyek megmutatják, hogyan regisztráljon részfizetéseket egy ügyfélhez és hogyan vegye igénybe a készpénzfizetési engedményeket a készpénzfizetési engedményi időszakban.
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37c378a424d89a884d1f3f0f14e1d544b3af178b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178164"
---
# <a name="settle-a-partial-customer-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Részleges vevői kifizetés kiegyenlítése és az utolsó részlet teljes kiegyenlítése a készpénzfizetési engedmény dátuma előtt

[!include [banner](../includes/banner.md)]

Ez a cikk olyan eseteket mutat be, amelyek megmutatják, hogyan regisztráljon részfizetéseket egy ügyfélhez és hogyan vegye igénybe a készpénzfizetési engedményeket a készpénzfizetési engedményi időszakban.

A FabriKam a 4028.-es számú vevőnek árut értékesít. A Gyár 1 százalékos készpénzfizetési engedményt ajánl, ha a számla 14 napon belül befizetésre kerül. A számlakat 30 napon belül be kell fizetni. A Fabrikam emellett a részleges kifizetésekra is nyújt készpénzfizetési engedményt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="customer-invoice"></a>Vevői számla
Június 25-én Arnie egy 1.000,00 értékű számlát rögzít és ad fel 4028-es vevő számára. Arnie megtekintheti ezt a tranzakciót a **Vevői tranzakciók** oldalon.

| Bizonylat   | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Számla          | 2015-06-25 | 10010   | 1000,00                             |                                       | 1000,00 | dollár      |

A **Vevő** vagy a **Vevői tranzakciók** lapon Arnie megnyithatja a **Tranzakciók kiegyenlítése** lapot, hogy megtekintse a számlához elérhető készpénzfizetési engedmények dátumait és összegeit. A határidő július 25, és egy 10,00 értékű készpénzfizetési engedmény érhető el, ha a számla kifizetése július 9-ig megtörténik.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015-07-25 | 10010   | 1000,00                       | dollár      | 990,00           |

Az engedményadatok **Tranzakciók kiegyenlítése** lap alján jelennek meg a kijelölt számlához.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 10,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 10,00     |

Arnie rákattint a **Készpénzfizetési engedmény** lapra, hogy megnézze az engedmény összegét.

| Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege | Összeg a tranzakció pénznemében. |
|--------------------|----------------------|--------------------------------|
| 2015-09-07           | 10,00                | 990,00                         |
| 2015-07-25          | 0,00                 | 1000,00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Részleges kifizetés a Vevői kifizetések rögzítése lapon
A 4028-as vevő elküld egy 500,00 összegű kifizetés július 1-jén. A kifizetés rögzítéséhez Arnie nem kattint a **Sorok** elemre. Ehelyett a kifizetés rögzítését egy új kifizetési napló készítésével, majd a **Vevői kifizetések rögzítése** lap megnyitásával teszi meg. Beviszi a kifizetési adatokat és megjelöli a rögzített számlát. Amikor Arnie az összeghez **500,00** értéket ad meg, akkor megadja még az **500,00** értéket a **Kifizetendő összeg** mezőben a rácsban. Mivel a Gyár engedélyezi a készpénzfizetési engedményt a részleges kifizetéseket látja, hogy 5,05 értékű részleges készpénzfizetési engedmény lesz még levonva. A számítás ehhez az engedményhez 500,00 ÷ 0,99 × 0,01 = 5,05. (Ebben a számításban az 500,00 0,99-el van osztva, mert 1% az engedmény. Ezért a vevő a számla 99 százalékát fizeti ki. Az eredmény ezután megszorzásra kerül az engedmény százalékával, ami 1 százalék, vagy 0,01. Ha a vevő a teljes 10,00 értékű engedményt igénybe veszi, akkor a kiegyenlítendő összeg 990,00 lesz.) Az engedményadatok a **Vevői kifizetések rögzítése** lapon található rács alján jelennek meg.

| Alkalmazandó készpénzfizetési engedmény összege | Alkalmazott készpénzfizetési engedmény | Fizetendő összeg |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Részleges kifizetés naplósorok használatával
Ahelyett, hogy megnyitná a **Vevői kifizetések rögzítése** lapot a kifizetési naplóban Arnie rákattint a **Sorok** elemre, hogy rögzítse a kifizetést. A kifizetési napló megjelenik, ahol Arnie rögzíthet egy sort a 4028-as vevőhöz. Anna ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a számlát kiegyenlítettnek jelölje. Arnie megjelöli a számlát és módosítja az értéket a **Kiegyenlítendő összeg** mezőben **500,00** értékre Ismét látja, hogy az érték a **Készpénzfizetési engedmény összege** mezőben **10,00** a teljes számlához és az érték a **Alkalmazandó készpénzfizetési engedmény összege** mezőben **5,05**. Ezért Arnie 505,05 értéket egyenlít ki ebből a számlából.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015-07-25 | 10010   | 1000,00                       | dollár      | 500,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 10,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 5,05      |

Ha a vevő pontosan a számla felét akarja kiegyenlíteni, akkor a vevő egy 495,00 összegű kifizetést ad fel. Ebben az esetben Arnie rögzít **495,00** összeget a **Kiegyenlítendő összeg** mezőben. Az 5,00 összegű készpénzfizetési engedmény is le lesz vonva, tehát a teljes kiegyenlített összeg 500,00.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10010 | 4028    | 2015-06-25 | 2015-07-25 | 10010   | 1000,00                       | dollár      | 495,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015-07-09 |
| Készpénzfizetési engedmény összege         | 10,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 5,00      |

Arnie bezárja a **Tranzakciók kiegyenlítése** lapot. 495,00 értékű kifizetési sor jön létre a naplóban, majd ezután Arnie feladja a naplót. Áttekintheti a vevői tranzakciókat a **Vevői tranzakciók** lapon. Ezen a lapon Arnie láthatja, hogy a számla egyenlege 500,00. Lát továbbá egy 495,00 összegű kifizetést és egy 5,00 összegű engedményt.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Számla          | 2015-06-25 | 10010   | 1000,00                             |                                       | 500,00  | dollár      |
| ARP-10010  |  Kifizetés         | 2015-01-07  |         |                                      | 495,00                                | 0,00    | dollár      |
| DISC-10010 |  Készpénzfizetési engedmény   | 2015-01-07  |         |                                      | 5,00                                  | 0,00    | dollár      |

## <a name="payment-for-the-remaining-amount"></a>A fennmaradó összeg kifizetése
A 4028-as vevő kifizeti a fennmaradó 495,00 összeget július 8-án, ami a készpénzfizetési engedmény időszakába esik. Arnie létrehoz egy kifizetési naplót július 8-án és megjelöli a tranzakciót kiegyenlítettnek. Látja, hogy a kiegyenlítendő összeg 495,00. Az érték a **Becsült készpénzfizetési engedmény** mezőben **5,00**, mert az 5,00 engedményt korábban már érvényesítették.

|                         |        |
|-------------------------|--------|
| Megjelölt összesen            | 495,00 |
| Becsült készpénzfizetési engedmény | 5,00   |

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

Arnie feladja ezt a naplót és áttekinti a vevői tranzakciókat a **Vevői tranzakciók** lapon. A számla egyenlege most 0,00 és Arnie látja a két kifizetést és a két készpénzfizetési engedményt.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Számla          | 2015-06-25 | 10010   | 1000,00                             |                                       | 0,00    | dollár      |
| ARP-10010  | Kifizetés          | 2015-01-07  |         |                                      | 495,00                                | 0,00    | dollár      |
| DISC-10010 | Készpénzfizetési engedmény    | 2015-01-07  |         |                                      | 5,00                                  | 0,00    | dollár      |
| ARP-10011  | Kifizetés          | 2015-08-07  |         |                                      | 495,00                                | 0,00    | dollár      |
| DISC-10011 | Készpénzfizetési engedmény    | 2015-08-07  |         |                                      | 5,00                                  | 0,00    | dollár      |





