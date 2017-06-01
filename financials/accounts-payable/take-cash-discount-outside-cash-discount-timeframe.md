---
title: "Készpénzfizetési engedmény érvényesítése a készpénzfizetési engedményi időszakon kívül"
description: "A cikk két esetet tartalmaz, amelyek megmutatják, hogyan írható jóvá a készpénzfizetési engedmény, akkor is, ha a kifizetés a készpénzfizetési engedmény időszakán kívül történt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 15da62064521ec614764c42b57a20d32b110587a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Készpénzfizetési engedmény érvényesítése a készpénzfizetési engedményi időszakon kívül

[!include[banner](../includes/banner.md)]


A cikk két esetet tartalmaz, amelyek megmutatják, hogyan írható jóvá a készpénzfizetési engedmény, akkor is, ha a kifizetés a készpénzfizetési engedmény időszakán kívül történt.

Június 28-én April egy 2.000,00 értékű számlát hoz létre 3052-es szállító számára. A számla 1 százalékos készpénzfizetési engedményt kínál, ha a számla 14 napon belül befizetésre kerül.

## <a name="use-cash-discount-option--always"></a>A Mindig készpénzfizetési engedménybállítás
April létrehoz egy kifizetést június 1-jén, ami az engedmény dátumánál későbbre esik. April megnyitja a **Tranzakciók kiegyenlítése** lapot, ahol megtekintheti azokat a tranzakciókat, amelyeket ki lehet egyenlíteni. 

Megjelöli a számlát kifizetéshez. Készpénzfizetési engedményre nem kerül sor, mert a fizetés túlnyúlik az engedményes időszakon. Azonban a szállító engedélyt adott Aprilnek, hogy mégis alkalmazhatja a készpénzfizetési engedményt. Ezért April a **Készpénzfizetési engedmény használata** mezőt átállítja **Mindig** beállításra.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Készpénzfizetési engedmény dátuma | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Mindig            | Inv-10030 | 3052    | 2015/6/28          | 2015/7/12 | 10030   | -2000,00                      | dollár      | -1980,00        |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/7/12 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Mindig    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Az engedmények számításához használandó dátum = kiválasztott dátum
Ha a számla és a fizetés is fel lett adva, a készpénzfizetési engedmény továbbra is igénybe vehető a tranzakció kiegyenlítésekor a a **Tranzakciók kiegyenlítése** oldalon. April **Az engedmények számításához használandó dátum** mezőt a **Kiválasztott dátum** beállításra módosítja. Ezután beírja június 28-át, ami a számla készpénzfizetési engedményének határideje. A rendszer ezt a dátumot használja a tranzakcióhoz tartozó készpénzfizetési engedmény kiszámítására. A **Nyitott tranzakciók kiegyenlítése** lapon April azt látja, hogy alapértelmezés szerint a teljes engedmény, vagyis 20,00 jelenik meg. A számlasor azt mutatja, hogy a kiegyenlítendő összeg 1980,00.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Készpénzfizetési engedmény dátuma | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva és kiemelve | Normál            | Inv-10030 | 3052    | 2015/6/28          | 2015/7/12 | 10030   | -2000,00                      | dollár      | -1980,00        |
| Kijelölve                 | Normál            | APP-10030 | 3052    | 2015-07-15          | 2015-07-15 |         | 500,00                         | dollár      | 500,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Az igénybe vett engedmény összege 20,00, mert a számla kiegyenlítendő összege az alapértelmezett összeg, vagyis 1980,00.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/7/12 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -20,00    |

April frissíti a **Kiegyenlítendő összeg** mezőt **500,00** értékre. Az érték az **Alkalmazandó készpénzfizetési engedmény összege** mezőben a számítás alapján **5,05** lesz.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kiválasztva és kiemelve | Normál            | Inv-10030 | 3052    | 2015/6/28 | 2015/7/12 | 10030   | 2,000.00                       | dollár      | -500,00          |
| Kijelölve                 | Normál            | APP-10030 | 3052    | 2015-07-15 | 2015-07-15 |         | 500,00                         | dollár      | 500,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg. Az **Alkalmazandó készpénzfizetési engedmény összege** mező értéke **5,05**, mert a számla kiegyenlítendő összegét a kifizetés összegére, 500,00 értékre módosították.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/7/12 |
| Készpénzfizetési engedmény összege         | -20,00    |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -5,05     |






