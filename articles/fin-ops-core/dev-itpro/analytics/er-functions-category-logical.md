---
title: A logikai kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott logikai függvényekről.
author: NickSelin
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43cbecf80ff70dac058977932c3a0bb03662cd98a88c68407051bdc584609d84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767194"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>A logikai kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) logikai függvényei segítségével logikai értékekkel dolgozhat, és egynél több összehasonlítást hajthat végre egyetlen kifejezésben, vagy több feltételt tesztelhet. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [És](er-functions-logical-and.md)                       | Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike igaz. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [Láda](er-functions-logical-case.md)                     | Ez a függvény kiértékeli a megadott kifejezés értékét a megadott alternatív beállításokkal, és visszaadja az első beállítás eredményét, amely megegyezik a megadott kifejezés értékével. Ellenkező esetben a nem kötelező alapértelmezett eredményt adja vissza, ha az alapértelmezett eredmény a hívott függvény utolsó argumentumaként van megadva, amelyet nem előz meg beállítás. A visszaadott érték bármely támogatott adattípus értéke lehet. |
| [Tartalmazza](er-functions-logical-contains.md)             | Ez a funkció határozza meg, hogy a megadott bemenet tartalmazza-e a megadott szöveget. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet tartalmazza-e a megadott szöveget. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [EndsWith](er-functions-logical-endswith.md)             | Ez a funkció határozza meg, hogy a megadott bemenet a megadott szöveggel végződik-e. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre végződik. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [Ha](er-functions-logical-if.md)                         | A függvény az első megadott értéket adja vissza a megadott feltétel teljesülése esetén. Ellenkező esetben a második megadott értéket adja vissza. A visszaadott érték bármely támogatott adattípus értéke lehet. |
| [Nem](er-functions-logical-not.md)                       | Ez a függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként. |
| [Or](er-functions-logical-or.md)                         | Ez a függvény **HAMIS** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike hamis. Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek bármelyike igaz. |
| [StartsWith](er-functions-logical-startswith.md)         | Ez a funkció határozza meg, hogy a megadott bemenet a megadott szöveggel kezdődik-e. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre kezdődik. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [ValueIn](er-functions-logical-valuein.md)               | Ez a függvény azt határozza meg, hogy a megadott bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Ez a függvény azt határozza meg, hogy a megadott *Int64* vagy *Egész szám* típusú bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |


## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]