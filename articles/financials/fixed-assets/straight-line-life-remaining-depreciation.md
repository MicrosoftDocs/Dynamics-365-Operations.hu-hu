---
title: "Lineáris - hátralevő élettartam értékcsökkenés"
description: "Ez a cikk a Lineáris-hátralevő élettartam értékcsökkenés módszeréről nyújt tájékoztatást."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ebca31727ecdaa2b94d4930174b2461845ab5578
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="straight-line-life-remaining-depreciation"></a>Lineáris - hátralevő élettartam értékcsökkenés

[!include [banner](../includes/banner.md)]

Ez a cikk a Lineáris-hátralevő élettartam értékcsökkenés módszeréről nyújt tájékoztatást.

Ha lineáris vagy degresszív tárgyieszköz-értékcsökkenési profilt állít be, akkor a **Lineáris - hátralevő élettartam** érték is választható az **Értékcsökkenési profilok** képernyő **Módszer** mezőjében, és az értékcsökkenési profilhoz társított tárgyi eszközök értékcsökkenésének az eszköz fennmaradó élettartama lesz az alapja. Ez általában időszakonként azonos értékcsökkenési összeget eredményez. A lineáris hátralévő élettartam típusú értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon. Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.

## <a name="select-a-depreciation-year"></a>Az értékcsökkenési év kiválasztása
Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon. Az alapértelmezett érték **Naptár**. A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások. Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.

### <a name="calendar"></a>Naptár

Ha a **Naptár** beállítást választja az ***Értékcsökkenési év*** mezőben, akkor az év január 1-től december 31-ig számít, akkor is, ha a pénzügyi év ettől eltérően van definiálva. A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül. Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték. Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló. Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   **Éves** felad egy összeget december 31-én.
-   **Havi**: felad egy havi összeget minden naptári hó végén.
-   **Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).
-   **Féléves**: féléves összeg feladása minden naptári félév végén (június 30. és december 31.).
-   **Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.

Ha például az **Éves** beállítást választja, az éves értékcsökkenés csak egyszer, minden év december 31-én kerül feladásra. Ha a **Havi** beállítást választja, a havi értékcsökkenés feladása havonta történik, az éves értékcsökkenési összeg egy-tizenkettedeként.

### <a name="fiscal"></a>Pénzügyi

Ha a **Pénzügyi** beállítást választja az **Értékcsökkenési év** mezőben, akkor a lineáris hátralévő élettartam típusú értékcsökkenési módszert alkalmazza a rendszer. Az értékcsökkenés számítása a fennmaradó pénzügyi év alapján történik. Egy 2015. július 1-től 2016. június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik. Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet. Az értékcsökkenés minden egyes pénzügyi időszak végén módosul. A következő üzleti év hossza a **Pénzügyi naptárak** oldalon meghatározott pénzügyi időszakoktól függ. Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:

-   Az **Éves** beállítás esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.
-   **Pénzügyi időszak**: az értékcsökkenés teljes értékét a pénzügyi évre számítja ki. Ezt az összeget azután a **Pénzügyi naptárak** lapon meghatározott pénzügyi időszakokra osztja fel a könyvnél meghatározott pénzügyi naptárra vonatkozóan.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Példa: változatlan tárgyi eszközök lineáris értékcsökkenése
Egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|                     |        |
|---------------------|--------|
| Beszerzési költség    | 11 000 |
| Maradványérték       | 1000  |
| Értékcsökkenés alapja   | 10 000 |
| Élettartam (év)  | 5      |
| Éves értékcsökkenés | 2 000  |

Az értékcsökkenési összeg minden évben megegyezik: (beszerzési ár - maradványérték) ÷ élettartam évei

| Időszak | Az éves értékcsökkenés-összeg számítása | Nettó könyv szerinti érték az év végén |
|--------|-----------------------------------------------|---------------------------------------|
| 1. év | (11 000 – 1000) ÷ 5 = 2000                  | 9000                                 |
| 2. év | (9000 – 1000) ÷ 4 = 2000                   | 7 000                                 |
| 3. év | (7000 – 1000) ÷ 3 = 2000                   | 5 000                                 |
| 4. év | (5000 – 1000) ÷ 2 = 2000                   | 3000                                 |
| 5. év | (3000 – 1000) ÷ 1 = 2000                   | 1000                                 |






