---
title: Szállítói kifizetés egy részének rendezése, amely több kedvezményes időszakkal rendelkezik
description: Ez a cikk egy olyan esetet mutat be, amely során több részleges kifizetés történik, egy több készpénzfizetési engedményt ajánló szállítónak.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da69d61c657ddc168a27a97fe16909d5f60eb4fd
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778037"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Szállítói kifizetés egy részének rendezése, amely több kedvezményes időszakkal rendelkezik

[!include [banner](../includes/banner.md)]

Ez a cikk egy olyan esetet mutat be, amely során több részleges kifizetés történik, egy több készpénzfizetési engedményt ajánló szállítónak. 

A 3054. szállító a Fabrikamnak 2 százalékos készpénzfizetési engedményt ad, ha a számlát öt napon belül kifizeti, és 1 százalékot, ha a számlát 14 napon belül kifizeti.

## <a name="invoice"></a>Számla
Június 28-én April egy 1.000,00 értékű számlát hoz létre 3054-es szállító számára. April megtekintheti ezt a tranzakciót a **Szállítói tranzakciók** oldalon.

| Bizonylat   | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg   | Pénznem |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 2020/28/6 | 10060   |                                      | 1,000.00                              | -1 000,00 | USD      |

A következő készpénzfizetési engedmény dátumok és az összegek érhetők el az aktuális számlához.

| Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege | Összeg a tranzakció pénznemében. |
|--------------------|----------------------|--------------------------------|
| 2020/3/7           | 20.00                | 980.00                         |
| 2020/12/7          | 10,00                | 990.00                         |
| 2020/25/7          | 0,00                 | 1,000.00                       |

## <a name="payment-on-july-2"></a>Kifizetés július 2-án
Július 2-án April szeretne kifizetni a számlájából 300,00 összegű részt. April egyszeri kifizetést hoz létre a Kötelezettségek **Fizetési napló** lapján. Felvesz egy sort a 3054. szállítónak, és beilleszti a fizetési összeget, amely **300,00**. April ezután megnyitja a **Tranzakciók kiegyenlítése** oldalt, hogy a kiegyenlítendő számlát kiegyenlítettnek jelölje. Frissíti az értéket a **Kiegyenlítendő összeg** mezőben, hogy az **300,00** legyen, és észleli, hogy az érték az **Alkalmazandó készpénzfizetési engedmény összege** mező **6,12** értékre változik. Mivel ezt kifizetést az engedmény első időszakában egyenlítik ki, ezért 2 százalékos engedmény vonatkozik rá.

| Jelölés | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normál            | Inv-10060 | 3054    | 2020/28/6 | 2020/28/7 | 10060   | 1,000.00                       | USD      | 300,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/02/7 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -6,12     |

Mivel készpénzfizetési engedmény érhető el, April módosítani szeretné a kifizetés összegét, hogy a teljes kiegyenlített összeg a kifizetés és a készpénzfizetési engedmény esetében is 300,00 legyen. Frissíti az értéket a **Kiegyenlítendő összeg** mezőben, hogy az **294,00** legyen, és észleli, hogy az érték az **Alkalmazandó készpénzfizetési engedmény összege** mezőben **6,00** értékre változik.

| Jelölés | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normál            | Inv-10060 | 3054    | 2020/28/6 | 2020/28/7 | 10060   | 1,000.00                       | USD      | 294,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/02/7 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -6,00     |

April ezután feladja ezt a fizetést. Megtekintheti ezt a tranzakciókat a **Szállítói tranzakciók** oldalon. Azt látja, hogy 300,00 érték alkalmazva lett a számlára. Ez az összeg 6,00 engedményt tartalmaz. A fennmaradó egyenleg ezért 700,00.

| Bizonylat    | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 2020/28/6 | 10060   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10060  | 2020/2/7  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2020/2/7  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Kifizetés július 8-án
Július 8-án April egy további kifizetést hajt végre a számla ellenében. Az összeg megadásához megnyitja a **Tranzakciók kiegyenlítése** lapot, majd rákattint a **Készpénzfizetési engedmény** lapra. Látja a két rendelkezésre álló készpénzfizetési engedmény dátumait és összegeit. Mivel ezt kifizetést az engedmény második időszakában egyenlítik ki, ezért 1 százalékos engedmény, vagy 5,00 vonatkozik rá. Ezt az összeget az 1000,00 az 1 %-os engedményeként vagy a 10,00 feleként számítjuk ki.

| Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege | Összeg a tranzakció pénznemében. |
|--------------------|----------------------|--------------------------------|
| 2020/3/7           | 20.00                | 680,00                         |
| 2020/12/7          | 10,00                | 690,00                         |
| 2020/25/7          | 0,00                 | 700.00                         |

April úgy dönt, 495,00-öt fizet, és az 5,00 készpénzfizetési engedményt kéri. Ezért a teljes elszámolt összeg 500,00 lesz.

| Jelölés | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normál            | Inv-10060 | 3054    | 2020/28/6 | 2020/28/7 | 10060   | 1,000.00                       | USD      | 495,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/12/7 |
| Készpénzfizetési engedmény összege         | -10,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | -6,00     |
| Alkalmazandó készpénzfizetési engedmény összege | -5,00     |

A **Szállítói tranzakciók** lapon April látja, hogy az új egyenleg 200,00.

| Bizonylat    | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 2020/28/6 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 2020/2/7  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2020/2/7  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 2020/12/7 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 2020/12/7 |         | 5.00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Kifizetés július 20-án
Július 20 April végső kifizetést hoz létre a 200,00 összeghez. Kedvezményre nem kerül sor, mert a fizetés túlnyúlik mindkét engedményes időszakon. A számla egyenlege 0,00.

| Bizonylat    | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 2020/28/6 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 2020/2/7  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2020/2/7  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 2020/12/7 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 2020/12/7 |         | 5.00                                 |                                       | 0,00    | USD      |
| APP-10062  | 2020/20/7 |         | 200.00                               |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
