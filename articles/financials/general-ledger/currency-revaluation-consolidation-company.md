---
title: "Devizaátértékelés konszolidált vállalatban"
description: "Ez a témakör azt ismerteti, hogyan lehet átértékelni a devizát a konszolidált vállalatban."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 27059b0d2a781453a7594bdc430005df6ea5c167
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a>Devizaátértékelés konszolidált vállalatban

[!include[banner](../includes/banner.md)]




Ha egy könyvelési pénznemből egy másikba konszolidál adatokat és változik az árfolyam, devizaátértékelést kell futtatnia, hogy a számlaegyenlegek átértékelése megfelelően történjen. Az adatok eredeti konszolidációja során használja a **Devizaátváltás** lapot, ahol kiválaszthatja a kezdeti árfolyamot a konszolidációs folyamat kezdeti átváltásához. Ha új árfolyamot ad meg (például következő hónapban), át kell értékelnie a számlaegyenlegeket. A nem realizált nyereség vagy nem realizált veszteség ezután az új árfolyamnak és dátumnak megfelelően frissül. Az alábbi példa a könyvelés bejegyzéseket mutatja be, amelyek egy ilyen folyamat során létrejönnek.

## <a name="company-setup"></a>Vállalat beállítása
-   **Forrás/működő vállalat (USMF)** – USA-dollárban (USD) van megadva a könyvelési és a jelentési pénznem.
-   **Konszolidált vállalat (CON)** – Euróban (EUR) van megadva a könyvelési és a jelentési pénznem.
    -   **Realizált nyereség** – 801500 főkönyvi számla
    -   **Realizált veszteség**– 801600 főkönyvi számla
    -   **Nem realizált nyereség**– 801600 főkönyvi számla
    -   **Nem realizált veszteség**– 801400 főkönyvi számla

## <a name="original-transactions"></a>Eredeti tranzakciók
### <a name="cash-receipt-transactions-in-usmf"></a>Készpénz-befizetési utalvány tranzakciói USMF-ben

| Dátum       | Főkönyvi számla               | Pénznem | Összeg |
|------------|------------------------------|----------|--------|
| 2015/11/10 | 110110 – készpénz                | dollár      | 500    |
| 2015/11/10 | 130100 – kinnlevőségek | dollár      | -500   |

## <a name="exchange-rates"></a>Árfolyamok
| Kezdő pénznem | Célpénznem | Kezdő dátum | Árfolyam |
|---------------|-------------|------------|---------------|
| HUF           | dollár         | 2015/1/10  | 200           |
| HUF           | dollár         | 2015/1/11  | 150           |
| HUF           | dollár         | 2012/1/12  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>2015 októberében a konszolidáció végrehajtása megtörténik
### <a name="balances-in-the-consolidation-company"></a>Egyenlegek a konszolidált vállalatban

| Főkönyvi számla | Pénznem | Összeg | Számítás    |
|----------------|----------|--------|----------------|
| 110110         | HUF      | 250    | 500 USD × 50%  |
| 130100         | HUF      | -250   | -500 USD × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>Devizaátértékelés végrehajtása 2015. október 1. és 2015. november 30. közötti számlákra
### <a name="balances-in-the-consolidation-company"></a>Egyenlegek a konszolidált vállalatban

| Főkönyvi számla | Pénznem | Összeg  | Számítás                        |
|----------------|----------|---------|------------------------------------|
| 110110         | HUF      | 333,33  | Eredeti összeg 500 × 66,6667%  |
| 130100         | HUF      | -333,33 | Eredeti összeg -500 × 66,6667% |
| 801400         | HUF      | 83,33   | 333,33 – 250                       |
| 801600         | HUF      | -83,33  | -333,33 – (-250)                   |

A jelentési pénznem összegeihez további tranzakciók történnek.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>Devizaátértékelés végrehajtása 2015. október 1. és 2015. december 31. közötti számlákra
### <a name="balances-in-the-consolidation-company"></a>Egyenlegek a konszolidált vállalatban

| Főkönyvi számla | Pénznem | Összeg  | Számítás                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | HUF      | 500,00  | Eredeti összeg 500 × 1                           |
| 130100         | HUF      | -500,00 | Eredeti összeg -500 × 1                          |
| 801400         | HUF      | 250     | 500 – 333,33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | HUF      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |






