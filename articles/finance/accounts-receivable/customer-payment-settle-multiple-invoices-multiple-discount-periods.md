---
title: Több, eltérő engedményidőszakra vonatkozó számla kiegyenlítése egy vevői kifizetéssel
description: Ez a cikk bemutatja, hogyan lehetséges több számlát is kifizetni akkor, ha az összes számla jogosult készpénzfizetési engedményre. Ebben cikkben bemutatott esetek rávilágítanak arra, hogy a készpénzfizetési engedmények, hogyan függnek a kifizetés idejétől.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6bf321a5b0511295f2500f10cdffa9ff6f043bff
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780242"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>Több, eltérő engedményidőszakra vonatkozó számla kiegyenlítése egy vevői kifizetéssel

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehetséges több számlát is kifizetni akkor, ha az összes számla jogosult készpénzfizetési engedményre. Ebben cikkben bemutatott esetek rávilágítanak arra, hogy a készpénzfizetési engedmények, hogyan függnek a kifizetés idejétől.

A Gyár a 4032.-es számú vevőnek árut értékesít. A Gyár 1 százalékos készpénzfizetési engedményt ajánl, ha a számla 14 napon belül befizetésre kerül. A Fabrikam emellett a részleges kifizetésekre is nyújt készpénzfizetési engedményt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="invoices"></a>Számlák
Vevői 4032 három számla van, amelynek 3000,00 összesen:

-   Az FTI-10040, 1000,00 értékű számla május 15-én került rögzítésre. Ez a számla 14 napon belüli kifizetés esetén 1 százalékos készpénzfizetési engedményre jogosult.
-   Az FTI-10041, 1000,00 értékű számla június 25-én került rögzítésre. Ez a számla 14 napon belüli kifizetés esetén 1 százalékos készpénzfizetési engedményre jogosult.
-   Az FTI-10042, 1000,00 értékű számla június 25-én került rögzítésre. Ez a számla 2 százalékos készpénzfizetési engedményre jogosult, ha öt napon belüli kifizetik és 1 százalékos engedményre, ha 14 napon belül fizetik ki.

## <a name="settle-all-invoices-on-june-29"></a>Minden számla kiegyenlítése június 29.
Anna a június 29 ezeket a számlákat teljesen kiegyenlítendő kifizetési naplót hoz létre, a kifizetés esetén 2970,00. Összes engedmény összege 30,00. Anna létrehoz egy kifizetést a vevő 4032 és megnyílik az **Tranzakciók kiegyenlítése** oldalon. Az **Tranzakciók kiegyenlítése** lapon Anna megjelölése kiegyenlítésre három számla egyes sorai:

-   A kifizetés, számla FTI-10040 1000,00. Alkalmazott készpénzfizetési engedmény a következőben.
-   A kifizetés, számla FTI-10041 990,00. A készpénzfizetési engedmény 1 százalék vagy 10,00 származik.
-   A kifizetés, számla FTI-10042 980,00. A készpénzfizetési engedmény 2 százalék vagy 20,00 származik.

| Jelölés | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum   | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|------|----------|-----------|---------|-----------|-----------|---------|---------------------|---------------------|----------|------------------|
| Kiválasztva     | Normál      | FTI-10040 | 4032    | 2020/15/5 | 2020/15/6 | 10040   | 1,000.00  |                    | USD      | 1,000.00         |
| Kiválasztva     | Normál      | FTI-10041 | 4032    | 2020/25/6 | 2020/25/7 | 10041   | 1,000.00  |                    | USD      | 990.00           |
| Kiválasztva és kiemelve | Normál      | FTI-10042 | 4032    | 2020/25/6 | 2020/25/7 | 10042   | 1,000.00    |              | USD      | 980.00           |

A kifizetés feladása után a a vevői egyenleg értéke 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Minden számla kiegyenlítése július 1.
Anna a július 1 ezeket a számlákat teljesen kiegyenlítendő kifizetési naplót hoz létre, a kifizetés esetén 2980,00. Anna létrehoz egy kifizetést a vevő 4032 és megnyílik az **Tranzakciók kiegyenlítése** oldalon. Az **Tranzakciók kiegyenlítése** lapon Anna megjelölése kiegyenlítésre három számla egyes sorai:

-   A kifizetés, számla FTI-10040 1000,00. Alkalmazott készpénzfizetési engedmény a következőben.
-   A kifizetés, számla FTI-10041 990,00. A készpénzfizetési engedmény 1 százalék vagy 10,00 származik.
-   A kifizetés, számla FTI-10042 990,00. A készpénzfizetési engedmény 1 százalék vagy 10,00 származik. Bár július 1-jén határideje, amely megfelel a 2 százalékos engedményt után, akkor még mindig határideje, amely megfelel az 1%-os engedményt.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|----------|---------|-----------|---------|-----------|-----------|---------|--------------------|------------------|----------|------------------|
| Kiválasztva         | Normál            | FTI-10040 | 4032    | 2020/15/5 | 2020/15/6 | 10040   | 1,000.00         |                | USD      | 1,000.00         |
| Kiválasztva                 | Normál            | FTI-10041 | 4032    | 2020/25/6 | 2020/25/7 | 10041   | 1,000.00  |               | USD      | 990.00           |
| Kiválasztva és kiemelve | Normál            | FTI-10042 | 4032    | 2020/25/6 | 2020/25/7 | 10042   | 1,000.00  |             | USD      | 990.00           |

## <a name="partial-settlement-on-june-29"></a>Részleges kiegyenlítés függőben június 29-én
Vevői 4032 kifizethet a részleges összeget, például minden egyes számlához felét. Anna létrehoz egy kifizetést a vevő 4032 és megnyílik az **Tranzakciók kiegyenlítése** oldalon. A **Tranzakciók kiegyenlítése** lapon Anna megjelölése kiegyenlítésre három számla egyes sorai. Az egyes sorokban Arnie felviszi a kiegyenlítendő összeg alapján, ha a vevő által adott utasításokat. Arnie kiválaszt egy sort, ha a sor engedményösszege és a készpénzfizetési engedmény összege, amely látja. Fél a számlát a vevő fizeti, mert Anna fér hozzá, amelyek értéke a **készpénzfizetési engedmény összege** mező FTI-10042 értéke **20,00**, de az érték a **alkalmazott készpénzfizetési engedmény** mező **10,00**. A kifizetés összege 1485,00.

| Jelölés   | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Pénznem | Kiegyenlítendő összeg |
|-------------|-------------------|-----------|---------|-----------|-----------|---------|-----------|------------------|----------|------------------|
| Kiválasztva   | Normál       | FTI-10040 | 4032    | 2020/15/5 | 2020/15/6 | 10040   | 1,000.00        |               | USD      | 500.00           |
| Kiválasztva                 | Normál            | FTI-10041 | 4032    | 2020/25/6 | 2020/25/7 | 10041   | 1,000.00     |     | USD      | 495,00           |
| Kiválasztva és kiemelve | Normál            | FTI-10042 | 4032    | 2020/25/6 | 2020/25/7 | 10042   | 1,000.00     |         | USD      | 490.00           |

Arnie manuálisan is megadhatja a 1485,00 értékű kifizetés összegét, mielőtt megnyitná a **Tranzakciók kiegyenlítése** oldalt. Ha Arnie kézzel beírja a kifizetés összegét, és megjelöli a három tranzakciót, de nem módosítja az értéket a **Kiegyenlítendő összeg** mezőben minden tranzakciónál, akkor a következő üzenetet kapja a lap bezárásakor:

> A jelölt tranzakciók összege eltér a napló összegétől. Módosítja a napló összegét?

Ha a kifizetés összege csak 1485,00 kell Arnie, kattint **Nem** , és ezt követően feladja a naplót. A tranzakció kiegyenlítése a következőképpen történik:

1.  Számla FTI-10040 teljesen ki van egyenlítve az 1000,00, mert május 15-én rögzítettek, és a legrégebbi számla. Alkalmazott készpénzfizetési engedmény a következőben. A fennmaradó összeg a tranzakció pénznemében 485,00.
2.  Számla FTI-10041 a egyáltalán nincs kiegyenlítve. Számlák FTI-10041 és FTI-10042 ugyanazon a napon írt be. Azonban 1%-os engedményt a számla FTI-10041 érhető el, és a 2 százalékos engedményt a számla FTI-10042 érhető el. Jobb engedményt és a számla FTI-10042 érhető el, mert a fennmaradó 485,00 FTI-10042 számla kiegyenlítése.
3.  A fennmaradó 485,00 számla FTI-10042 kiegyenlítése. A gyár részleges engedmények kínál. Ebben az esetben az engedmény a 9,90 (= 485,00–0,98. x 0,02). Az összeg (485,00) elosztja 0,98, mert 2 százalékos engedményt (ennek megfelelően a vevő kifizeti a számla 98 százaléka). Az eredmény ezután megszorzásra kerül az engedmény százalékával, ami 2 százalék. 485,00 kifizetését, valamint a kedvezmény 9,90 az egyenlő 494,90. A számlasorhoz tartozó eredeti összeg 1000,00. A tranzakció ezért egyenlege a 505,10 (= 1000,00 – 494,90).

Arnie megtekintheti ezt az információt a **Vevői tranzakciók** oldalon.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Számla          | 2020/15/5 | 10040   | 1,000.00                             |                                       | 0,00     | USD      |
| FTI-10041  | Számla          | 2020/25/6 | 10041   | 1,000.00                             |                                       | 1,000.00 | USD      |
| FTI-10042  | Számla          | 2020/25/6 | 10042   | 1,000.00                             |                                       | 505.10   | USD      |
| ARP-10040  | Kifizetés          | 2020/29/6 |         |                                      | 1,485.00                              | 0,00     | USD      |
| DISC-10040 | Készpénzfizetési engedmény    | 2020/29/6 |         |                                      | 9,90                                  | 0,00     | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
