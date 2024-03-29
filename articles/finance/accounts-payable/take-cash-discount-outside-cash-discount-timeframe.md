---
title: Készpénzfizetési engedmény érvényesítése a készpénzfizetési engedményi időszakon kívül
description: A cikk két esetet tartalmaz, amelyek megmutatják, hogyan írható jóvá a készpénzfizetési engedmény, akkor is, ha a kifizetés a készpénzfizetési engedmény időszakán kívül történt.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780238"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Készpénzfizetési engedmény érvényesítése a készpénzfizetési engedményi időszakon kívül

[!include [banner](../includes/banner.md)]

A cikk két esetet tartalmaz, amelyek megmutatják, hogyan írható jóvá a készpénzfizetési engedmény, akkor is, ha a kifizetés a készpénzfizetési engedmény időszakán kívül történt.

Június 28-én April egy 2.000,00 értékű számlát hoz létre 3052-es szállító számára. A számla 1 százalékos készpénzfizetési engedményt kínál, ha a számla 14 napon belül befizetésre kerül.

## <a name="use-cash-discount-option--always"></a>A Mindig készpénzfizetési engedménybállítás
April létrehoz egy kifizetést június 1-jén, ami az engedmény dátumánál későbbre esik. April megnyitja a **Tranzakciók kiegyenlítése** lapot, ahol megtekintheti azokat a tranzakciókat, amelyeket ki lehet egyenlíteni. 

Megjelöli a számlát kifizetéshez. Készpénzfizetési engedményre nem kerül sor, mert a fizetés túlnyúlik az engedményes időszakon. Azonban a szállító engedélyt adott Aprilnek, hogy mégis alkalmazhatja a készpénzfizetési engedményt. Ezért April a **Készpénzfizetési engedmény használata** mezőt átállítja **Mindig** beállításra.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Készpénzfizetési engedmény dátuma | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva | Mindig            | Inv-10030 | 3052    | 2020/28/6          | 2020/12/7 | 10030   | -2000,00                      | USD      | -1980,00        |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/12/7 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Az engedmények számításához használandó dátum = kiválasztott dátum
Ha a számla és a fizetés is fel lett adva, a készpénzfizetési engedmény továbbra is igénybe vehető a tranzakció kiegyenlítésekor a a **Tranzakciók kiegyenlítése** oldalon. April **Az engedmények számításához használandó dátum** mezőt a **Kiválasztott dátum** beállításra módosítja. Ezután beírja június 28-át, ami a számla készpénzfizetési engedményének határideje. A rendszer ezt a dátumot használja a tranzakcióhoz tartozó készpénzfizetési engedmény kiszámítására. A **Nyitott tranzakciók kiegyenlítése** lapon April azt látja, hogy alapértelmezés szerint a teljes engedmény, vagyis 20,00 jelenik meg. A számlasor azt mutatja, hogy a kiegyenlítendő összeg 1980,00.

| Jelölés          | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Készpénzfizetési engedmény dátuma | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva és kiemelve | Normál    | Inv-10030 | 3052    | 2020/28/6         | 2020/12/7 | 10030   | -2000,00                      | USD      | -1980,00        |
| Kiválasztva                 | Normál    | APP-10030 | 3052    | 2020/15/7          | 2020/15/7 |         | 500.00                         | USD      | 500.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Az igénybe vett engedmény összege 20,00, mert a számla kiegyenlítendő összege az alapértelmezett összeg, vagyis 1980,00.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/12/7 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -20,00    |

April frissíti a **Kiegyenlítendő összeg** mezőt **500,00** értékre. Az érték az **Alkalmazandó készpénzfizetési engedmény összege** mezőben a számítás alapján **5,05** lesz.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva és kiemelve | Normál            | Inv-10030 | 3052    | 2020/28/6 | 2020/12/7 | 10030   | 2,000.00                       | USD      | -500,00          |
| Kiválasztva                 | Normál            | APP-10030 | 3052    | 2020/15/7 | 2020/15/7 |         | 500.00                         | USD      | 500.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Az **Alkalmazandó készpénzfizetési engedmény összege** mező értéke **5,05**, mert a számla kiegyenlítendő összegét a kifizetés összegére, 500,00 értékre módosították.

| Mező                        | Érték     |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2020/12/7 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
