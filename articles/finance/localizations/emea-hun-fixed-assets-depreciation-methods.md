---
title: Tárgyi eszközök értékcsökkenési módjai Magyarország esetében
description: Ez a témakör a magyarországi jogi személyek tárgyi eszközeinek értékcsökkenésével kapcsolatban tartalmaz tájékoztatást.
author: Anasyash
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 274443
ms.assetid: fb4084cf-1061-4286-9f09-0f28a031483d
ms.search.region: Hungary
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 3a0fbadace164a3e434b32b23311e651da2a8173
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815015"
---
# <a name="fixed-assets-depreciation-methods-for-hungary"></a>Tárgyi eszközök értékcsökkenési módjai Magyarország esetében

[!include [banner](../includes/banner.md)]

Ez a témakör a magyarországi jogi személyek tárgyi eszközeinek értékcsökkenésével kapcsolatban tartalmaz tájékoztatást. Magyarországon a következő négy országspecifikus értékcsökkenési mód létezik:

-   Egyenes (Magyarország)
-   Szorzótényező
-   Faktor (Magyarország)
-   Évek összegének számjegyei

Az egyes értékcsökkenési módokban az értékcsökkenési összeg kiszámítása az egyes időszakok naptári napjain alapul a magyar vállalati adózási törvények előírásai alapján. Az értékcsökkenési szabályok le vannak tiltva a kapcsolódó értékcsökkenési profilokban.

## <a name="depreciation-method-straight-line-hungary"></a>Értékcsökkenési mód: lineáris (Magyarország)
Ha tárgyieszköz-értékcsökkenési profilt állít be, és a **Lineáris (Magyarország)** lehetőséget választja az **Értékcsökkenési mód** mezőben, akkor az ehhez az értékcsökkenési profilhoz társított eszközök értékcsökkenése az eszközök teljes élettartamán és az egyes időszakok napjainak tényleges számán fog alapulni.

### <a name="example-straight-line-hungary-depreciation"></a>Példa: Lineáris (Magyarország) értékcsökkenés

Tegyük fel, hogy egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|    &nbsp;          | &nbsp;                                |
|--------------------|---------------------------------------|
| Beszerzési költség   | 120 000                               |
| Beszerzési dátum   | Január 1.                             |
| Élettartam (év) | 5                                     |
| Élettartam napokban  | 1826 (= 365 + 365 + 365 + 366 + 365) |
| Időszak gyakorisága   | Évente                                |

Az éves értékcsökkenési összeg az év naptári napjai alapjul: Értékcsökkenés összege = Beszerzési költség ÷ Napok összesített száma x Az egyes időszakok napjainak száma Az alábbi táblázat a Lineráris (Magyarország) értékcsökkenési módszer számítási eredményeit, összehasonlításképpen pedig a [Lineáris, élettartam szerinti értékcsökkenés](../fixed-assets/straight-line-service-life-depreciation.md) számítási eredményeit jeleníti meg.

| Időszak | Napok száma | Lineáris (Magyarország) értékcsökkenés összege | Lineáris, élettartam szerinti értékcsökkenés összege |
|--------|----------------|-------------------------------------------------|----------------------------------------------------|
| 1. év | 365            | 23 986,86 (= 120 000 ÷ 1826 × 365)             | 24 000 (= 120 000 ÷ 5)                             |
| 2. év | 365            | 23 986,86 (= 120 000 ÷ 1826 × 365)             | 24 000 (= 120 000 ÷ 5)                             |
| 3. év | 365            | 23 986,86 (= 120 000 ÷ 1826 × 365)             | 24 000 (= 120 000 ÷ 5)                             |
| 4. év | 366            | 24 052,57 (= 120 000 ÷ 1826 × 366)             | 24 000 (= 120 000 ÷ 5)                             |
| 5. év | 365            | 23 986,86 (= 120 000 ÷ 1826 × 365)             | 24 000 (= 120 000 ÷ 5)                             |

## <a name="depreciation-method-multiplication-factor"></a>Értékcsökkenési mód: szorzótényező
Ha beállít egy tárgyi eszközök értékcsökkenésével kapcsolatos profilt, és a **Szorzótényező** értéket választja az **Értékcsökkenési mód** mezőben, akkor az ehhez az értékcsökkenési profilhoz társított eszközök esetében az értékcsökkenés számítása egyedi százalékértékek alapján történik minden évben. Ezeket a százalékokat a **Kézi ütemezések** gyorslapon állíthatja be. A százalékos értékek összege kötelezően 100.

### <a name="example-multiplication-factor-depreciation"></a>Példa: Szorzótényezős értékcsökkenés

Tegyük fel, hogy egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|  &nbsp;            | &nbsp;    |
|--------------------|-----------|
| Beszerzési költség   | 120 000   |
| Beszerzési dátum   | Január 1. |
| Élettartam (év) | 2         |
| Időszak gyakorisága   | Évente    |

A következő táblázat a kézi ütemezéseket mutatja be.

| Intervallum száma | Százalék | Halmozott százalékos érték |
|-----------------|------------|-----------------------|
| 2               | 60%        | 100%                  |
| 1               | 40%        | 40%                   |

Az éves értékcsökkenési összeg az év manuális százalékán alapul: Értékcsökkenési összeg = Beszerzési költség x Százalék Az alábbi táblázat a Szorzótényezős értékcsökkenési módot mutatja be, amikor az időszak gyakoriságának beállítása **Éves**.

| Időszak | Szorzótényezős értékcsökkenés összege |
|--------|-----------------------------------------------|
| 1. év | 48 000 (= 120 000 × 40%)                      |
| 2. év | 72 000 (= 120 000 × 60%)                      |

Ha egy egységhez beállított időszak gyakorisága kisebb, mint az **Éves** (például **Féléves**, **Negyedéves** vagy **Havi**), az éves értékcsökkenési összeget a rendszer az egyes időszakokra osztja el. Az elosztás az év napjainak számán (365 vagy 366) és az adott időszak hosszán alapul. Az alábbi táblázat a Szorzótényezős értékcsökkenési mód számítási eredményeit mutatja be, amikor az időszak gyakoriságának beállítása **Féléves**.

| Időszak     | Napok száma | Szorzótényezős értékcsökkenés összege |
|------------|----------------|-----------------------------------------------|
| H1, 1. év | 181            | 23 802,74 (= 48 000 ÷ 365 × 181)              |
| H2, 1. év | 184            | 24 197,26 (= 48 000 ÷ 365 × 184)              |
| H1, 2. év | 181            | 35 704,11 (= 72 000 ÷ 365 × 181)              |
| H2, 2. év | 184            | 36 295,89 (= 72 000 ÷ 365 × 181)              |

## <a name="depreciation-method-factor-hungary"></a>Értékcsökkenési mód: tényező (Magyarország)
Ha beállít egy tárgyi eszközök értékcsökkenésével kapcsolatos profilt, és a **Tényező (Magyarország)** értéket választja az **Értékcsökkenési mód** mezőben, akkor az ehhez az értékcsökkenési profilhoz társított eszközök esetében az értékcsökkenés számítása a **Tényező** mezőben beállított egyetlen százalékérték alapján történik minden évben.

### <a name="example-factor-hungary-depreciation"></a>Példa: Tényezős (Magyarország) értékcsökkenés

Tegyük fel, hogy egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|  &nbsp;            | &nbsp;    |
|--------------------|-----------|
| Beszerzési költség   | 120 000   |
| Beszerzési dátum   | Január 1. |
| Élettartam (év) | 2         |
| Időszak gyakorisága   | Évente    |
| Szorzó             | 50        |

Az éves értékcsökkenési összeg az év tényezős százalékán alapul: Értékcsökkenési összeg = Beszerzési költség x Tényező (százalék) Az alábbi táblázat a Tényezős értékcsökkenési módot mutatja be, amikor az időszak gyakoriságának beállítása **Éves**.

| Időszak | Tényezős (Magyarország) értékcsökkenés összege |
|--------|------------------------------------------|
| 1. év | 60 000 (= 120 000 × 50%)                 |
| 2. év | 60 000 (= 120 000 × 50%)                 |

Ha egy egységhez beállított időszak gyakorisága kisebb, mint az **Éves** (például **Féléves**, **Negyedéves** vagy **Havi**), az éves értékcsökkenési összeget a rendszer az egyes időszakokra osztja el. Az elosztás az év napjainak számán (365 vagy 366) és az adott időszak hosszán alapul. Az alábbi táblázat a Tényezős (Magyarország) értékcsökkenési mód számítási eredményeit mutatja be, amikor az időszak gyakoriságának beállítása **Féléves**.

| Időszak     | Napok száma | Tényezős (Magyarország) értékcsökkenés összege |
|------------|----------------|------------------------------------------|
| H1, 1. év | 181            | 29 753,42 (= 60 000 ÷ 365 × 181)         |
| H2, 1. év | 184            | 30 246,58 (= 60 000 ÷ 365 × 184)         |
| H1, 2. év | 181            | 29 753,42 (= 60 000 ÷ 365 × 181)         |
| H2, 2. év | 184            | 30 246,58 (= 60 000 ÷ 365 × 184)         |

## <a name="depreciation-method-sum-of-years-digits"></a>Értékcsökkenési mód: Évek összegének számjegyei
Ha beállít egy tárgyi eszközök értékcsökkenésével kapcsolatos profilt, és az **Évek összegének számjegyei** értéket választja az **Értékcsökkenési mód** mezőben, akkor az ehhez az értékcsökkenési profilhoz társított eszközök esetében az értékcsökkenés számítása a beszerzési ár és egy százalékérték alapján történik, amely minden évben csökken. A százalék értéke élettartam éveitől függ.

### <a name="example-sum-of-years-digits-depreciation"></a>Példa: Évek összegének számjegyei értékcsökkenése

Tegyük fel, hogy egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|  &nbsp;            | &nbsp;    |
|--------------------|-----------|
| Beszerzési költség   | 120 000   |
| Beszerzési dátum   | Január 1. |
| Élettartam (év) | 4         |
| Időszak gyakorisága   | Évente    |

Az éves értékcsökkenési összeg az adott évre kiszámított százalékon alapul. Az alábbi táblázat az Évek összegének számjegyei értékcsökkenési mód számítási eredményeit mutatja be, amikor az időszak gyakoriságának beállítása **Éves**. Évek összegének számjegyei = 10 (= 4 + 3 + 2 + 1)

| Időszak | Százalék     | Évek összegének számjegyei összege |
|--------|----------------|----------------------------------------------|
| 1. év | 40% (= 4 ÷ 10) | 48 000 (= 120 000 × 40%)                     |
| 2. év | 30% (= 3 ÷ 10) | 36 000 (= 120 000 × 30%)                     |
| 3. év | 20% (= 2 ÷ 10) | 24 000 (= 120 000 × 20%)                     |
| 4. év | 10% (= 1 ÷ 10) | 12 000 (= 120 000 × 10%)                     |

Ha egy egységhez beállított időszak gyakorisága kisebb, mint az **Éves** (például **Féléves**, **Negyedéves** vagy **Havi**), az éves értékcsökkenési összeget a rendszer az egyes időszakokra osztja el. Az elosztás az év napjainak számán (365 vagy 366) és az adott időszak hosszán alapul. Az alábbi táblázat az Évek összegének számjegyei értékcsökkenési mód egy évre vonatkozó számítási eredményeit mutatja be, amikor az időszak gyakoriságának beállítása **Féléves**.

| Időszak     | Százalék     | Napok száma | Évek összegének számjegyei összege |
|------------|----------------|----------------|----------------------------------------------|
| H1, 1. év | 40% (= 4 ÷ 10) | 181            | 23 802,74 (= 48 000 ÷ 365 × 181)             |
| H2, 1. év | 40% (= 4 ÷ 10) | 184            | 24 197,26 (= 48 000 ÷ 365 × 184)             |





[!INCLUDE[footer-include](../../includes/footer-banner.md)]