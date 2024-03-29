---
title: Felhasználás értékcsökkenése
description: Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5597e2d960f5d6393515370d3495b77569191b5
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712397"
---
# <a name="consumption-depreciation"></a>Felhasználás értékcsökkenése

[!include [banner](../includes/banner.md)]

Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.

Ha beállít egy tárgyi eszközök értékcsökkenésével kapcsolatos profilt, és a **Felhasználás** lehetőséget választja ki a **Mód** mezőben az **Értékcsökkenési profilok** oldalán, akkor az ehhez az értékcsökkenési profilhoz társított tárgyi eszközök értékcsökkenése a tárgyi eszközök használatán alapul. Nem kell a százalékos értékeket és az időszakokat beállítsani az **Értékcsökkenési profilok** oldalon. Miután létrehozta a Felhasználási módot alkalmazó értékcsökkenési profilt, többféle módon is beállíthatja a módszert.

## <a name="set-up-and-use-consumption-depreciation"></a>Felhasználási értékcsökkenés beállítása és használata
1.  Az **Értékcsökkenési profilok** oldalon hozza létre az értékcsökkenési profilt. A felhasználási számításokhoz az értékcsökkenési profilnak tartalmaznia kell egy azonosítót és egy nevet és **Felhasználás** lehetőséget ki kell választani a **Módszer** mezőben.
2.  Az **Felhasználási tényezők** lapon állítsa be a felhasználási tényezőket. Minden felhasználási tényezőnek rendelkeznie kell egy Azonosítóval és egy névvel és egy felhasználási tényezővel, amely vagy mennyiségben vagy százalékban van meghatározva.
3.  Az **Felhasználási egységek** lapon állítsa be a felhasználási egységeket. Minden egyes felhasználási egységnek azonosítóval és névvel kell rendelkeznie. A felhasználási értékcsökkenést a felhasználási értékcsökenés kiszámítására használják a **Felhasználási értékcsökkenés** oldalon. Az egység lehet például kilométer (km), kilogramm (kg) és óra.
4.  A **Tárgyi eszközök** lapon állítsa be az egyes tárgyi eszközöket. Az értékcsökkenési profiloktárgyi eszközhoz válassza ki az értékcsökkenési profillal rendelkező értékmodelleket és értékcsökkenési könyveket. Be kell állítania az értékmodelleket vagy az értékcsökkenési könyveket a felhasználási értékcsökkenéshez, ha a tárgyi eszközök bármelyike a a Felhasználási módszeren alapuló értékcsökkenési profilokat használja. Ezzel a beállítással végezheti el vagy a **Érték modellek** oldal **Értékcsökkenés** lapján vagy a **Értékcsökkenési profil** oldal **Általános** gyorslapján. Ugyanaz az értékmodell több tárgyi eszközhöz is használható. Az értékcsökkenési profilok a tárgyi eszközhöz választott értékmodell vagy értékcsökkenési könyv részei. Nem lehet hozzáadni vagy módosítani az értékcsökkenési profilokat közvetlenül a **Tárgyi eszközök** oldalon. Az értékcsökkenési profilokat csak módosítani lehet az **Értékcsökkenés könyvek** lapon.
5.  Az **Értékmodellek** lapon vagy a **Értékcsökkenési könvyek** lapon, a **Felhasználási értékcsökkenés** mező csoportban adja meg az információkat a következő mezókben:
    -   Felhasználási tényező
    -   Egység
    -   Egység értékcsökkenése
    -   Becsült felhasználás

    A **Megadott felhasználás** mező mutatja azon felhasználási értékcsökkenést egységekben, amelyet már megadtak vagy a tárgyi eszközök és értékmodellek kombinációja vagy az értékcsökkenési könyv részére. Ebben a mezőben nem frissítheti manuálisan az értéket.

## <a name="examples"></a>Példák
### <a name="example-1"></a>1. példa

Az alábbi felhasználási tényező van beállítva január 31-re vonatkozóan:

-   A mennyiség 1,000.
-   A tárgyi eszközhöz megadott egység értékcsökkenési ár 1,5.

Január 31-i értékcsökkenési javaslat a következőképpen történik: Mennyiség x 1000 x 1,5 = 1500, ha a tárgyi eszköz számára megadott tényező egy százalékos tényező, a **Becsült felhasználás** mezőben megbecsült mennyiség megszorozzák a kiválasztott záró dátumhoz beállított százalékkal. Az így kapott mennyiséget a program majd az időszak értékcsökkenési mennyiségeként javasolja.

### <a name="example-2"></a>2. példa

Január 31-ére vonatkozóan az alábbi tényező van beállítva a felhasználási értékcsökkenéshez:

-   A százalékos érték 10 százalék.
-   A tárgyi eszközhöz megadott egység értékcsökkenési ár 1,5.
-   A tárgyi eszköz becsült mennyisége 2 000.

Január 31-i értékcsökkenési javaslat a következőképpen történik: Becsült mennyiség x Százalék x Egység értékcsökkenése 2 000 x.10 x 1,5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
