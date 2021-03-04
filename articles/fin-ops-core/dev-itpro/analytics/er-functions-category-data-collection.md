---
title: Az adatgyűjtés kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott adatgyűjtési függvényekről.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 0ec6092f2992df91433bb8aaa4212fca2a0abf7c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686293"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Az adatgyűjtés kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) adatgyűjtési függvényei az éppen futtatott ER formátumban történő számlálásra és összegzésre használhatók a már létrehozott **Szöveg** vagy **Xml** formátumban előállított kimeneti adatok alapján. Ez a módszer használható a futtatott ER-formátum teljesítményének javítására, a létrehozott dokumentumokban lévő folyó összértékek értékeinek megadására az előállított dokumentumokban, és egyéb célokra. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Ez a függvény olyan *Rekordlista* értéket ad eredményül, amely tartalmazza azon értékek listáját, amelyeket a formátumelemek **Gyűjtött adatkulcs értéke** tulajdonsága adott vissza, és amelyeket akkor gyűjtött, amikor a formátumelemeket kimenő dokumentum létrehozására használták a formátumfuttatás során, és amelyek teljesítik a megadott követelményeket. Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz. |
| [CountIF](er-functions-datacollection-countif.md) | Ez a függvény egy *Egész* értéket ad eredményül, amely azoknak a formátumelemeknek a számát adja vissza, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt. A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz. |
| [CountIFs](er-functions-datacollection-countifs.md) | Ez a függvény egy *Egész* értéket ad eredményül, amely azoknak a formátumelemeknek a számát adja vissza, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételeket. Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az aktuális ER formátum elemének nevét jelöli. |
| [SumIF](er-functions-datacollection-sumif.md) | Ez a függvény egy *Valós* értéket ad eredményül, amely a formátumelemek kötései által visszaadott értékek összegét mutatja, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt. A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Ez a függvény egy *Valós* értéket ad eredményül, amely a formátumelemek kötései által visszaadott értékek összegét mutatja, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételeket. Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]