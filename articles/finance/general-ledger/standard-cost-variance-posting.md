---
title: Elszámoló költségeltérés feladása
description: Ez a témakör az elszámoló költségszámítás feladási profiljainak beállításával kapcsolatban tartalmaz tájékoztatást.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: bc4f1bd7c1bf7a8f214f20460b10d371d8f3c790
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804638"
---
# <a name="standard-cost-variance-posting"></a>Elszámoló költségeltérés feladása

Ha a szervezetben egy vagy több termékhez elszámolóáras költségszámítást használ, [konfigurálnia kell az elszámolóáras költségszámítás előfeltételeit](/supply-chain/cost-management/prerequisites-standard-costs.md). Ez a témakör leírja a 3. lépéshez szükséges feladási számlákat "Főkönyvi számlák hozzárendelése az elszámolóköltség-különbözetekkel kapcsolatos cikkfeladáshoz" témakörben.

A beszerzések és a termelési rendelések különböző típusú eltérések fordulhatnak elő. A termelési eltérésekre vonatkozó példákat lásd [a termelési különbözetek közös forrásait](/supply-chain/cost-management/common-sources-of-production-variances.md). A beszerzési rendelés áreltérései akkor lépnek fel, amikor a beszerzett cikkre elszámolóárat használ, és a beszerzési rendelésen eltérés van a termék elszámolóára és a számlázott összeg között.

## <a name="sample-posting-profile-configuration"></a>Minta feladási profil konfigurációja

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra. Minta fő számlákat és leírásokat tartalmaz.

- A "Tartozik/Követel" A <a0/<a0/<a2/1><a2/5>oszlop jelzi, hogy a tranzakció általában tartozik vagy követel. Bizonyos esetekben a tranzakció tartozásokat és jóváírásokat is feladhat.
- Az "Elszámolószámla" oszlop azt jelzi, hogy a feladás típusa elszámolószámla. Más szóval az erre a számlára feladott összeg automatikusan sztornírozódik egy későbbi tranzakció feladása során.
- A "P/F" oszlop jelzi a feladás típusát. A "P" a tényleges feladást, az "F" a pénzügyi feladást jelenti.
- A "Követés" oszlop jelzi, hogy a feladási típus fő számlája általában megegyezik-e egy másik feladási típus fő számlájával. Ez a jellemzően azt a feladási típust jelzi, amelyet általában használ.

> [!NOTE]
> A táblázatban szereplő fő számlák és fő számlák nevei csak javaslatok. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Beszerzési árkülönbözet | 510310 | Beszerzési árkülönbözet | Költség | Vagy | Nem | P | Nem alkalmazható | Erre a számlára akkor van szükség, ha eltérés van a beszerzési rendelés beszerzési ára és elszámolóára között. |
| Készletköltség átértékelése | 510330 | Készletköltség átértékelése | Költség | Vagy | Nem | P | Nem alkalmazható | Ez a számla akkor használatos, amikor egy elszámolóár cikkhez új költségszámítási verziót aktiválnak az aktuális készlet átértékelésekor. |
| Költségváltozási eltérés | 510320 | Költségváltozási eltérés | Költség | Vagy | Nem | P | Nem alkalmazható | Ez a számla akkor használatos, ha a helyek elszámolóárai között eltérés van, vagy ha egy cikket visszaküldnek, és a termék eredeti elszámolóára és aktuális elszámolóára között változás történik. |
| Termelési adagméret eltérése | 510370 | Termelési adagméret eltérése | Költség | Vagy | Nem | P | Nem alkalmazható | Ezt a számlát akkor használja a rendszer, ha eltérések vannak az anyagjegyzék-számítás alapja és a termelési rendelés költségszámításának tényleges mennyisége között. |
| Termelési árkülönbözet | 510340 | Termelési árkülönbözet | Költség | Vagy | Nem | P | Nem alkalmazható | Erre a számlára akkor van szükség, ha árkülönbség van a becsült költség és a termelési rendelés tényleges költsége között. |
| Termelési mennyiségi eltérés | 510350 | Termelési mennyiségi eltérés | Költség | Vagy | Nem | P | Nem alkalmazható | Ezt a számlát akkor használja a program, ha mennyiségi különbségek vannak a becsült költség és a termelési rendelés tényleges költségei között. |
| Termeléshelyettesítési eltérés | 510360 | Termeléshelyettesítési eltérés | Költség | Vagy | Nem | P | Nem alkalmazható | Erre a számlára akkor van szükség, ha egy termelési rendeléshez nem várt felhasználás történik. |
| Kerekítési eltérés | 618160 | Kerekítési különbözet | Költség | Vagy | Nem | P | Nem alkalmazható | Ezt a számlát akkor használja a program, ha kerekítési különbözet van, amikor a termelési költségek számítása az elszámoló költségekből történik. |
