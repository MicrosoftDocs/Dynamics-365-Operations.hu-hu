---
title: Szabadság- és távollétkoncepciók
description: Ez a témakör leírja a szabadság és távollét fogalmakat, és azt hogyan történik a szabadidő-egyenlegek meghatározása.
author: andreabichsel
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: ''
ms.openlocfilehash: 03e2557e29194f17a9a586470ced5b352408b07c
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898642"
---
# <a name="leave-and-absence-concepts"></a>Szabadság- és távollétkoncepciók

Az ebben a témakörben ismertetett fogalmak és feltételek segítségével meghatározható, hogy hogyan kaphat az alkalmazott szabadságot, és hogy történik az alkalmazott időegyenlegének kiszámítása. Szabadság és távollét kezelésével kapcsolatos további tudnivalókat lásd: [Szabadság és a távollét kezelése](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Szabadságterv részletei

### <a name="start-date"></a>Kezdés dátuma

Kezdő dátum az a dátum, amikor a könyvelési folyamat megkezdődik. Áthozott összegek számításához használt évfordulóként is szolgál a kezdő dátum.

## <a name="accruals"></a>Könyvelések

Könyvelések határozzák meg, hogy mikor és milyen gyakran kaphat az alkalmazott eltávozást. Az elhatárolások megadásával kapcsolatos irányelveket, illetve az arányosítással kapcsolatos irányelvek a **Könyvelések** szakaszban adhatók meg a szabadság- és távollétterv beállítása során.

### <a name="accrual-frequency"></a>Könyvelés gyakorisága

A könyvelés gyakorisága meghatározza, hogy milyen gyakran történik a szabadság könyvelése vagy megadása. Ehhez a következő lehetőségek állnak rendelkezésre:

- Napi
- Heti
- Kéthetente
- Félhavonta
- Havi
- Negyedéves
- Félévente
- Évente
- Egyik sem

### <a name="accrual-period-basis"></a>Könyvelési időszak alapja

A könyvelési periódus alapja határozza meg a dátumot, a mely a könyvelési időszakok kiszámításához használatos. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Terv kezdő dátuma**
- **Munkavállalóspecifikus dátum** – Ha ezt a lehetőséget választja, az érték határozza meg a kezdeti dátum értékének forrását, amely a könyvelési időszakok kiszámításához használatos. Ehhez a következő lehetőségek állnak rendelkezésre:

    - Egyéni
    - Évforduló dátuma
    - Eredeti felvételi dátum
    - Szolgálati idő dátuma
    - A dolgozó módosított kezdési dátuma
    - A dolgozó kezdési dátuma

### <a name="accrual-award-date"></a>Elhatárolás jutalmazásának dátuma

A könyvelés megadásának dátuma határozza meg, hogy mikor kaphat az alkalmazott eltávozást. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Könyvelési időszak záró dátuma** – Az alkalmazott a megadott időszak utolsó napján kap eltávozást.

    A helyes összeg könyveléséhez a könyvelési folyamatnak az egész időszakot magában kell foglalnia. Például könyvelési időszaka 2018 január 1-től 2018 január 31-ig tart. Ebben az esetben, hogy januárt is tartalmazza, a könyvelést 2018. február 1-jén kell futtatni.

- **Könyvelési időszak kezdő dátuma** – Az alkalmazott a megadott időszak első napján kap eltávozást.

### <a name="accrual-policy-on-enrollment"></a>A belépésre vonatkozó könyvelési irányelv

A belépésre vonatkozó könyvelési irányelv határozza meg a könyvelési számítási módját, ha az alkalmazott egy könyvelési időszak során van beléptetve. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Arányosított** – A felvétel dátuma és a kezdő dátum közötti dátumtartomány szolgála a különbség meghatározására napokban. Ez a különbség lesz alkalmazva a könyvelések feldolgozása során.
- **Teljes könyvelés** – A teljes könyvelési összeg, a szint alapján oda lesz ítélve az első könyvelési feldolgozás során.
- **Nincs elhatárolási** – Nincs növekvény alkalmazva a következő könyvelési időszakig.

### <a name="accrual-policy-on-unenrollment"></a>A kilépésre vonatkozó könyvelési irányelv

A kilépésre vonatkozó könyvelési irányelv határozza meg a könyvelési számítási módját, ha az alkalmazott egy könyvelési időszak során van kiléptetve. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Arányosított** – A felvétel dátuma és a kezdő dátum közötti dátumtartomány szolgála a különbség meghatározására napokban. Ez a különbség lesz alkalmazva a könyvelések feldolgozása során.
- **Teljes könyvelés** – A teljes könyvelési összeg, a szint alapján oda lesz ítélve az első könyvelési feldolgozás során.
- **Nincs elhatárolási** – Nincs növekvény alkalmazva a következő könyvelési időszakig.

## <a name="accrual-schedule"></a>Könyvelési ütemezés

A könyvelési ütemezés határozza meg, hogy egy alkalmazotthoz hogyan lesz könyvelve a távollét és milyen összegek elhatárolása és továbbvitele történik az alkalmazottnál. Szintek hozhatók létre, hogy az eltávozást különféle szintek alapján lehessen megítélni.

### <a name="months-of-service"></a>Munkaviszony hossza hónapokban

A **Munkaviszonyban töltött hónapok** határozza meg a minimális hónapok számát, amelyet az alkalmazottak kell dolgozniuk, hogy elhatárolásra legyenek jogosultak. Ha nem szükséges minimum az alkalmazottak számára, az érték legyen **0**.

### <a name="hours-worked"></a>Ledolgozott órák

A **Ledolgozott órák** határozza meg a minimális órák számát, amelyet az alkalmazottak kell dolgozniuk egy könyvelési időszakban, hogy könyvelésre legyenek jogosultak. Ha nem szükséges minimum az alkalmazottak számára, az érték legyen **0**.

### <a name="accrual-amount"></a>Halmozódás összege

A könyvelési összeg az órák vagy napok száma amelyet az alkalmazottak összegyűjtenek időszakonként. Az időszak a könyvelés gyakoriságán alapul.

### <a name="minimum-balance"></a>Minimális egyenleg

Negatív érték használható a minimális egyenleghez, ha az alkalmazottak több eltávozást kérhetnek, mint amennyivel rendelkeznek.

### <a name="maximum-carry-forward"></a>Maximális áthozat

A könyvelési folyamat igazítja azokat az egyenelegeket, amelyek meghaladják a maximális átviteli egyenleget a kezdő dátum évfordulóján.

### <a name="grant-amount"></a>Megítélés mennyisége

A megítélés mértéke a kezdeti órák vagy napok száma, amelyet az alkalmazottaknak megítélnek amikor először bekerülnek az eltávozási tervbe. Összeg a könyvelésinem lesz elhatárolva minden könyvelési időszakhoz.

## <a name="enrollments-and-balances"></a>Beléptetések és egyenlegek

### <a name="enrollment-date"></a>Regisztráció dátuma

A beléptetés dátuma határozza meg, hogy egy alkalmazott mikor kezdheti meg az eltávozás elhatárolását. Például ha az alkalmazott 2018. június 15-én van felvéve egy szabadságtervbe, nem határolhat el eltávozást 2018 június 15. előtt.

### <a name="current-balance"></a>Aktuális egyenleg

Az aktuális egyenleg az eltávozás kérelmekhez rendelkezésre álló szabadság. Ez az összeg tartalmazza az elhatárolásokat, jóváhagyott kérelmek és korrekciókat az aktuális dátumig.

### <a name="current-balance-examples"></a>Példa az aktuális egyenlegre

#### <a name="annual-plan"></a>Éves terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/1        | Éves            | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2019. január 1. (1/1/2019), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Aktuális egyenleg (160) = Könyvelési összeg (200) – Kérelem összege (40)

#### <a name="semimonthly-plan"></a>Félhavi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2018. május 1. (5/1/2018), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Aktuális egyenleg (22) = Könyvelési összeg (5 × 6) – Kérelem összege (8)

#### <a name="monthly-plan"></a>Havi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2018. május 1. (5/1/2018), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Aktuális egyenleg (7) = Könyvelési összeg (5 × 3) – Kérelem összege (8)

### <a name="forecasted-balance"></a>Előrejelzett egyenlegek

Az *előrejelzett egyenleg* a szabadság mennyisége, amely egy jövőbeni dátumon érhető el. Könyvelések és áthozott helyesbítések addig az időpontig vannak előrejelezve.

A konvertálás az alábbi képlet alapján történik:

Hétfő előre jelzett egyenlege = Aktuális egyenleg – Kérelmek + könyvelések – áthozott kiigazítások

### <a name="forecasted-balance-examples"></a>Előre jelzett egyenleg – példák

#### <a name="annual-plan"></a>Éves terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/1        | Éves            | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2019. február 15. (2/15/2019), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Előrejelzett egyenleg (40) = Könyvelési érték (20) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

#### <a name="semimonthly-plan"></a>Félhavi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2019. február 15. (2/15/2019), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Előrejelzett egyenleg (35) = Könyvelési érték (5 × 3) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

#### <a name="monthly-plan"></a>Havi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

Könyvelések feldolgozása 2019. február 15. (2/15/2019), úgy, hogy a teljes időszak be van foglalva.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Előrejelzett egyenleg (30) = Könyvelési érték (10 × 1) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

### <a name="proration-balance-examples"></a>Arányosított egyenlegek – példák

#### <a name="prorated-monthly-plan"></a>Arányosított havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3,00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 2,53    |

#### <a name="full-accrual-monthly-plan"></a>Teljes könyvelési havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3,00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Nincs könyvelési havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3,00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 2.00    |
