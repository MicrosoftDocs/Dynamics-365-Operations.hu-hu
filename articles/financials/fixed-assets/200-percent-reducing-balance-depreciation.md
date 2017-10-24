---
title: "200 százalék degresszív értékcsökkenés"
description: "Ez a cikk a 200 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 46afd002a370a43c9e1d2fb7cc5e61ece9033be9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="200-percent-reducing-balance-depreciation"></a>200 százalék degresszív értékcsökkenés

[!include[banner](../includes/banner.md)]


Ez a cikk a 200 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.

Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **200% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkentve lesznek ugyanazzal százalékos értékkel, ami az egyes értékcsökkenési időszakoknál szerepel. A százalék kiszámítása az eszköz élettartama alapján történik. Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 40% lesz (200% ÷ 5). 

Ez a módszer duplán degresszív értékcsökkenésként is ismert.

200 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon. Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.

## <a name="select-a-depreciation-year"></a>Az értékcsökkenési év kiválasztása
Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon. Az alapértelmezett érték **Naptár**. 

A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások. Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.

### <a name="calendar"></a>Naptár

Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**. 

A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül. Jellemzően az értékcsökkenés a nettó könyv szerinti érték mínusz a maradványérték. Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló. 

Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   **Éves** felad egy összeget december 31-én.
-   **Havi**: felad egy havi összeget minden naptári hó végén.
-   **Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).
-   **Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).
-   **Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.

### <a name="fiscal"></a>Pénzügyi

Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési** év mezőben, akkor a 200 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon. A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be. 

Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik. Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet. Az értékcsökkenés minden időszakhoz helyesbítve van. A következő üzleti év hossza az időszakok beállítása alapján van meghatározva a **Pénzügyi naptárak** oldalon. 

Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként, a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   Az **Éves** esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.
-   **Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre. Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.

## <a name="example-of-200-reducing-balance-depreciation"></a>Példa a 200% degresszív értékcsökkenésre
|                                |        |
|--------------------------------|--------|
| Beszerzési költség               | 11 000 |
| Maradványérték                  | 1 000 |
| Értékcsökkenés alapja              | 10 000 |
| Élettartam (év)             | 5      |
| Éves százalékos értékcsökkenés | 40%    |

A 200% degresszív értékcsökkenési módszer elosztja a 200 százalékot az élettartam éveivel. Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.

| Időszak | Az éves értékcsökkenés-összeg számítása | Könyv szerinti érték             | Nettó könyv szerinti érték az év végén |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| 1. év | (11 000 – 1 000) × 40% = 4 000                | 11 000 – 4 000 = 7 000 | 11 000 – 1 000 – 4 000 = 6 000        |
| 2. év | 6 000 × 40% = 2 400                           | 7 000 – 2 400 = 4 600  | 6 000 – 2 400 = 3 600                 |
| 3. év | 3 600 × 40% = 1 440                           | 4 600 – 1 440 = 3 160  | 3 600 – 1 440 = 2 160                 |

> [!NOTE] 
> Általában amikor az összeg számolása a 200% degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.




