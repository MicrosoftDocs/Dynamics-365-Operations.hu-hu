---
title: A logikai kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott logikai függvényekről.
author: NickSelin
manager: kfend
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686186"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>A logikai kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) logikai függvényei segítségével logikai értékekkel dolgozhat, és egynél több összehasonlítást hajthat végre egyetlen kifejezésben, vagy több feltételt tesztelhet. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [És](er-functions-logical-and.md)                       | Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike igaz. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [Láda](er-functions-logical-case.md)                     | Ez a függvény kiértékeli a megadott kifejezés értékét a megadott alternatív beállításokkal, és visszaadja az első beállítás eredményét, amely megegyezik a megadott kifejezés értékével. Ellenkező esetben a nem kötelező alapértelmezett eredményt adja vissza, ha az alapértelmezett eredmény a hívott függvény utolsó argumentumaként van megadva, amelyet nem előz meg beállítás. A visszaadott érték bármely támogatott adattípus értéke lehet. |
| [Ha](er-functions-logical-if.md)                         | A függvény az első megadott értéket adja vissza a megadott feltétel teljesülése esetén. Ellenkező esetben a második megadott értéket adja vissza. A visszaadott érték bármely támogatott adattípus értéke lehet. |
| [Nem](er-functions-logical-not.md)                       | Ez a függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként. |
| [Or](er-functions-logical-or.md)                         | Ez a függvény **HAMIS** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike hamis. Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek bármelyike igaz. |
| [ValueIn](er-functions-logical-valuein.md)               | Ez a függvény azt határozza meg, hogy a megadott bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Ez a függvény azt határozza meg, hogy a megadott *Int64* vagy *Egész szám* típusú bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |


## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]