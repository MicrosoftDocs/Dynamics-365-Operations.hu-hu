---
title: Készpénzfizetési engedmények túlfizetések esetére
description: Ez a cikk azokat az eseteket mutatja be, amelyek megmutatják a fizetés kezelésének módját, amikor a felhasználó a készpénzfizetési engedményt tesz, de a túlfizetés esetében is.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f0714eab80f43695b2b93f77a70f31c360277f9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444121"
---
# <a name="cash-discounts-for-overpayments"></a>Készpénzfizetési engedmények túlfizetések esetére

[!include [banner](../includes/banner.md)]

Ez a cikk azokat az eseteket mutatja be, amelyek megmutatják a fizetés kezelésének módját, amikor a felhasználó a készpénzfizetési engedményt tesz, de a túlfizetés esetében is. 

Egy számla akkor tekinthető túlfizetettnek, ha a kifizetési összeg nagyobb, mint a készpénzfizetési engedmény összegével csökkentett számlaösszeg. Annak beállításához, hogy hogyan kezelje a rendszer az elérhető készpénzfizetési engedménykülönbséget, ha egy számlát túlfizetnek, a **Készpénzfizetési engedmény adminisztrációja** és a **Maximális túl- vagy alulfizetés** mezőket kell beállítania a **Kinnlevőségek paraméterei** oldalon. A következő példában a vevő túlfizetett egy számlát 0,50 értékkel.

| Számla összege | Készpénzfizetési engedmény elérhető | A készpénzfizetési engedmény beszámításával fizetendő összeg | A vevő által ténylegesen kifizetett összeg |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00        | 10,50                   | 94,50                                               | 95,00                             |

## <a name="cash-discount-administration--specific"></a>Készpénzfizetési engedmény adminisztrációja = Meghatározott
Ha a **Meghatározott** beállítás van kiválasztva a **Készpénzfizetési engedmény adminisztrációja** mezőben, a **Automatikus tranzakciókhoz használt számlák** lapon, akkor a rendszer a teljes készpénzfizetési engedményt alkalmazza. A túlfizetés összegét vagy feladja egy készpénzfizetési engedménykülönbözeti főkönyvi számlára vagy megmarad a vevői számla egyenlegén. A rendszer viselkedése attól függ, hogy a túlfizetés összege 0,00 és a **Maximális túl- vagy alulfizetés** mezőben megadott összeg között van, vagy meghaladja a **Maximális túl- vagy alulfizetés** összegét.

### <a name="scenario-1"></a>1. eset

Ebben az esetben a túlfizetés értéke nulla és a maximális túlfizetés vagy alulfizetés között van. Egy 105,00 értékű számla kerül rögzítésre, amelyhez készpénzfizetési engedmény érhető el, ha a számla hét napon belül kiegyenlítésre kerül.

| Számla összege | Készpénzfizetési engedmény elérhető | A készpénzfizetési engedmény beszámításával fizetendő összeg |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

A vevő a készpénzfizetési engedmény időszakában elküld egy 95,00 értékű kifizetést. A kifizetés a 105,00 értékű számla kiegyenlítésére történik. Miután a számlák és fizetések kiegyenlítésre kerültek, a következő tranzakciók jönnek létre a Kinnlevőségek modulban a vevő számára.

| Tranzakció   | Összeg | Egyenleg |
|---------------|--------|---------|
| Számla       | 105,00 | 0,00    |
| Kifizetés       | -95,00 | 0,00    |
| Készpénzfizetési engedmény | -10,50 | 0,00    |

A következő könyvelési tételek a kifizetéshez és a kiegyenlítéshez jönnek létre. **Fizetés**

| Fiók             | Terhelés összege | Követelés összege |
|---------------------|--------------|---------------|
| Készpénz                | 95,00        |               |
| Kinnlevőségek |              | 95,00         |

**Elszámolás**

| Fiók                                                                                                          | Terhelés összege | Követelés összege |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Készpénzfizetési engedmény (A **Vevői engedmények fő számlája** mező a **Készpénzfizetési engedmények** lapon)                 | 10,50        |               |
| Kinnlevőségek                                                                                              |              | 10,50         |
| Vevői készpénzfizetési engedmény (A **Vevői engedmény** mező a **Számlák automatikus tranzakciókhoz** lapon) |              | 0,50          |
| Kinnlevőségek                                                                                              | 0,50         |               |

### <a name="scenario-2"></a>2. eset

Ebben az esetben a túlfizetési összeg értéke meghaladja a maximális túlfizetés vagy alulfizetés összegét. Egy 105,00 értékű számla kerül rögzítésre, amelyhez készpénzfizetési engedmény érhető el, ha a számla hét napon belül kiegyenlítésre kerül.

| Számla összege | Készpénzfizetési engedmény elérhető | A készpénzfizetési engedmény beszámításával fizetendő összeg |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

A vevő a készpénzfizetési engedmény időszakában elküld egy 95,00 értékű kifizetést. A kifizetés a 105,00 értékű számla kiegyenlítésére történik. Miután a számlák és fizetések kiegyenlítésre kerültek, a következő tranzakciók jönnek létre a Kinnlevőségek modulban a vevő számára.

| Tranzakció   | Összeg | Egyenleg |
|---------------|--------|---------|
| Számla       | 105,00 | 0,00    |
| Kifizetés       | -95,00 | -0,50   |
| Készpénzfizetési engedmény | -10,50 | 0,00    |

A 0,50 értékű túlfizetési összeg megmarad nyitott egyenlegként a fizetésen, és kiegyenlíthető lesz egy másik számlával szemben. A következő könyvelési tételek a kifizetéshez és a kiegyenlítéshez jönnek létre. **Fizetés**

| Fiók             | Terhelés összege | Követelés összege |
|---------------------|--------------|---------------|
| Készpénz                | 95,00        |               |
| Kinnlevőségek |              | 95,00         |

**Elszámolás**

| Fiók                                                                                          | Terhelés összege | Követelés összege |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Készpénzfizetési engedmény (A **Vevői engedmények fő számlája** mező a **Készpénzfizetési engedmények** lapon) | 10,50        |               |
| Kinnlevőségek                                                                              |              | 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Készpénzfizetési engedmény adminisztrációja = Meghatározatlan
Ha a **Meghatározatlan** beállítás van kiválasztva a **Készpénzfizetési engedmény adminisztrációja** mezőben, a **Automatikus tranzakciókhoz használt számlák** lapon, akkor a készpénzfizetési engedmény összege lecsökken a túlfizetés összegével. A rendszer mindig alkalmazza ezt a viselkedést, függetlenül attól, hogy a túlfizetett összeg meghaladja vagy elmadar a **Maximális túl- vagy alulfizetés** mezőben megadott összegtől.

### <a name="scenario-3"></a>3. eset

Ebben az esetben egy 105,00 értékű számla kerül rögzítésre, amelyhez készpénzfizetési engedmény érhető el, ha a számla hét napon belül kiegyenlítésre kerül.

| Számla összege | Készpénzfizetési engedmény elérhető | A készpénzfizetési engedmény beszámításával fizetendő összeg |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

A vevő a készpénzfizetési engedmény vége előtt elküld egy 95,00 értékű kifizetést. A kifizetés a 105,00 értékű számla kiegyenlítésére történik. Miután a számlák és fizetések kiegyenlítésre kerültek, a következő tranzakciók jönnek létre a Kinnlevőségek modulban a vevő számára.

| Tranzakció   | Összeg | Egyenleg |
|---------------|--------|---------|
| Számla       | 105,00 | 0,00    |
| Kifizetés       | -95,00 | -0,00   |
| Készpénzfizetési engedmény | -10,00 | 0,00    |

A készpénzfizetési engedmény 10,50 értékről 10,00 értékre csökken. A kifizetés és a számla kiegyenlítettnek tekinthető. **Fizetés**

| Számla             | Tartozik összeg | Jóváírás összege |
|---------------------|--------------|---------------|
| Készpénz                | 95,00        |               |
| Kinnlevőségek |              | 95,00         |

**Elszámolás**

| Fiók                                                                                          | Terhelés összege | Követelés összege |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Készpénzfizetési engedmény (A **Vevői engedmények fő számlája** mező a **Készpénzfizetési engedmények** lapon) | 10,50        |               |
| Kinnlevőségek                                                                              |              | 10,50         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]