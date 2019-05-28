---
title: 125 százalékos degresszív értékcsökkenés
description: Ez a cikk a 125 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7af5413376a98c3b2b7ded46c757c9156a3fadf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555696"
---
# <a name="125-percent-reducing-balance-depreciation"></a>125 százalékos degresszív értékcsökkenés

[!include [banner](../includes/banner.md)]

Ez a cikk a 125 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.

Amikor beállít egy tárgyieszköz-értékcsökkenési profilt a **125% degresszív** értéket választja a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkenése ugyanazzal százalékos értékkel lesz egyenlő, ami az egyes értékcsökkenési időszakoknál szerepel. A százalék kiszámítása az eszköz élettartama alapján történik. Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 25% lesz (125% ÷ 5).

125 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon. Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.

## <a name="select-a-depreciation-year"></a>Az értékcsökkenési év kiválasztása
Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon. Az alapértelmezett érték **Naptár**. 

A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások. Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.

### <a name="calendar"></a>Naptár

Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**. 

A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül. Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték. Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló. 

Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   **Éves** felad egy összeget december 31-én.
-   **Havi**: felad egy havi összeget minden naptári hó végén.
-   **Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).
-   **Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).
-   **Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.

### <a name="fiscal"></a>Pénzügyi

Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési év** mezőben, akkor a 125 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon. A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be. 

Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik. Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet. Az egyes időszakokban az értékcsökkenés automatikusan módosul, és a következő naptári év hossza a **Pénzügyi naptárak** oldalon található időszakok beállítása alapján történik. 

Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   Az **Éves** esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.
-   **Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre. Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.

## <a name="example-of-125-reducing-balance-depreciation"></a>Példa a 125% degresszív értékcsökkenésre

|                                |        |
|--------------------------------|--------|
| Beszerzési költség               | 11 000 |
| Maradványérték                  | 1000  |
| Értékcsökkenés alapja              | 10 000 |
| Élettartam (év)             | 5      |
| Éves százalékos értékcsökkenés | 25%    |

A 125% degresszív értékcsökkenési módszer elosztja a 125 százalékot az élettartam éveivel. Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.

| Időszak | Az éves értékcsökkenés-összeg számítása | Könyv szerinti érték                    | Nettó könyv szerinti érték az év végén |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| 1. év | (11 000 – 1000) × 25% = 2500                | (11 000 – 2500) = 8500      | (11 000 – 1000 – 2500) = 7500      |
| 2. év | 7500 × 25% = 1875                           | (8500 – 1875) = 6625       | (7500 – 1875) = 5625               |
| 3. év | 5625 × 25% = 1406,25                        | (6625 – 1406,25) = 5218,75 | (5625 – 1406,25) = 4218,75         |

> [!NOTE] 
> Általában amikor az összeg számolása a 125 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz, mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamra létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.



