---
title: Lineáris – élettartam szerinti értékcsökkenés
description: Ez a cikk a Lineáris, élettartam szerinti értékcsökkenés módszeréről nyújt tájékoztatást.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b7b9b240156263b4dc1bc308a7f4457380a27f3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178075"
---
# <a name="straight-line-service-life-depreciation"></a>Lineáris – élettartam szerinti értékcsökkenés

[!include [banner](../includes/banner.md)]

Ez a cikk a Lineáris, élettartam szerinti értékcsökkenés módszeréről nyújt tájékoztatást.

Ha lineáris vagy degresszív tárgyieszköz-értékcsökkenési profilt állít be, akkor a Lineáris - hátralevő élettartam érték is választható az Értékcsökkenési profilok képernyő Módszer mezőjében, és az értékcsökkenési profilhoz társított tárgyi eszközök értékcsökkenésének az eszköz fennmaradó élettartama lesz az alapja. Ez általában időszakonként azonos értékcsökkenési összeget eredményez. 

Csak akkor lesz különbség a lineáris hátralévő élettartam alapján és a lineáris élettartam alapján számított értékcsökkenési összeg között, ha módosítást adnak fel az eszközhöz. 

A lineáris hátralévő élettartam típusú értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az Értékcsökkenési év mezőben és az Időszak-gyakoriság mezőben az Értékcsökkenési profilok lapon.

## <a name="select-a-depreciation-year"></a>Az értékcsökkenési év kiválasztása
Kiválaszthatja a Naptár vagy Pénzügyi elemeket az Értékcsökkenési év mezőben az Értékcsökkenési profilok lapon. A kiválasztás függvényében változnak az Időszak gyakorisága mezőben elérhető beállítások. Az alapértelmezett beállítás a Naptár.

### <a name="calendar"></a>Naptár

Naptár választása esetén az év január 1-től december 31-ig számít, akkor is, ha a tárgyieszköznaptár vagy a főkönyvi időszakok ettől eltérően vannak definiálva. 

A Naptár beállítás használata esetén a rendszer minden évben január elsején frissíti az értékcsökkenés alapját, amely jellemzően a nettó könyv szerinti érték csökkentve a maradványértékkel. Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló. 

A Naptár lehetőség választása esetén a következő beállítások állnak rendelkezésre az Időszak gyakorisága mezőben, amelyek egész évben meghatározzák az értékcsökkenés feladási időpontját és összegét:
-   Éves felad egy összeget december 31-én.
-   Havonta: felad egy havi összeget minden naptári hó végén.
-   Negyedévente: Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).
-   Féléves: féléves összeg feladása minden naptári félév végén (június 30. és december 31.).
-   A Naponta lehetőséget választva minden nap feladható egy tranzakció a napi értékcsökkenés módszerrel számolt értékcsökkenés összegével.

Ha például az Évente beállítást választja, az éves értékcsökkenés csak egyszer, minden év december 31-én kerül feladásra. Ha a Havonta beállítást választja, a havi értékcsökkenés feladása havonta történik, az éves értékcsökkenési összeg egy-tizenkettedeként.

### <a name="fiscal"></a>Pénzügyi

Ha a Pénzügyi beállítást választja az Értékcsökkenési év mezőben, akkor a lineáris hátralévő élettartam típusú értékcsökkenési módszert alkalmazza a rendszer. Ezt a rendszer a pénzügyi év alapján számítja ki, amelyet a könyvnél meghatározott pénzügyi naptár, vagy a Főkönyv lapon kiválasztott pénzügyi naptár definiál. A pénzügyi naptárak a Pénzügyi naptárak oldalon állíthatóak be.

Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik. Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet. Az értékcsökkenés minden egyes pénzügyi időszak végén módosul. A következő pénzügyi év hossza az új pénzügyi évnek a Pénzügyi naptárak lapon való létrehozásakor beállított pénzügyi időszakoktól függ. 

Ha a Pénzügyi beállítást választja, az alábbi opciók lesznek elérhetőek az az Időszak gyakorisága mezőben:
-   Az Éves beállítás esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.
-   Pénzügyi időszak az üzleti évre vonatkozó teljes értékcsökkenési összeg kiszámítása, majd az Pénzügyi naptárak képernyőn vagy az egyes pénzügyi évek tárgyieszköznaptárán beállított pénzügyi időszakoknak megfelelő felbontása.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Példa: változatlan tárgyi eszközök lineáris értékcsökkenése
Tegyük fel, hogy egy tárgyi eszköz a következő jellemzőkkel rendelkezik.

|                     |        |
|---------------------|--------|
| Beszerzési költség    | 11 000 |
| Maradványérték       | 1000  |
| Értékcsökkenés alapja   | 10 000 |
| Élettartam (év)  | 5      |
| Éves értékcsökkenés | 2 000  |

Minden évben azonos értékcsökkenési összeget eredményez. (Beszerzési ár - Maradványérték) / Élettartam években

| Időszak | Az éves értékcsökkenési összeg számítása | Nettó könyv szerinti érték az év végén |
|--------|-------------------------------------------|---------------------------------------|
| 1. év | (11 000-1000)/5 = 2000              | 9 000                                 |
| 2. év | (11 000-1000)/5 = 2000              | 7 000                                 |
| 3. év | (11 000-1000)/5 = 2000              | 5 000                                 |
| 4. év | (11 000-1000)/5 = 2000              | 3000                                 |
| 5. év | (11 000-1000)/5 = 2000              | 1000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Példa: Módosított tárgyi eszközök lineáris értékcsökkenése

Most tegyük fel, hogy ugyanehhez a tárgyi eszközhöz a 2. évben hozzáadunk egy 4000 értékű beszerzés-módosítást. 

A beszerzés-módosítás élettartama azonos a tárgyi eszköz élettartamával, és a beszerzés idején kezdődik. A nettó könyv szerinti érték megmarad az 5. év végén, a beszerzés-módosítás nettó könyv szerinti értékének megfelelően. Az időszakos értékcsökkenés kiszámítása az alábbi táblázatban leírt módon történik.

| Időszak | Az éves értékcsökkenési összeg számítása | Nettó könyv szerinti érték az év végén |
|--------|-------------------------------------------|---------------------------------------|
| 1. év | 10 000/5 = 2000                        | 11 000 - 2000 = 9000                |
| 2. év | 4000 (beszerzés helyesbítése)            | 9000 + 4000 =13 000                 |
| 2. év | 14 000/5 = 2800                        | 13 000-2800 = 10 200               |
| 3. év | 14 000/5 = 2800                        | 10 200 - 2800 = 7400                |
| 4. év | 14 000/5 = 2800                        | 7400 - 2800 = 4600                 |
| 5. év | 14 000/5 = 2800                        | 4600 - 2800 = 1800                 |
| 6. év | Maradék: 800\*                           | 1800 – 800 = 1000                   |

\*Mivel a maradék összeg kisebb az értékcsökkenés összegénél, ezért csak a maradványérték lesz kiszámítva.





