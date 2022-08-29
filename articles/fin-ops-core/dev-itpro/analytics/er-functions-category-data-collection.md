---
title: Az adatgyűjtés kategóriába tartozó ER-függvények listája
description: Ez a cikk az Elektronikus jelentés (ER) által támogatott adatgyűjtési funkciókkal kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/04/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e01bed49646ffe344004f9eb51e9013e1b4c5430
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286149"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Az adatgyűjtés kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) adatgyűjtési függvényei az éppen futtatott ER formátumban történő számlálásra és összegzésre használhatók a már létrehozott **Szöveg** vagy **Xml** formátumban előállított kimeneti adatok alapján. Ez a módszer használható a futtatott ER-formátum teljesítményének javítására, a létrehozott dokumentumokban lévő folyó összértékek értékeinek megadására az előállított dokumentumokban, és egyéb célokra. Ez a témakör összefoglalást nyújt a funkciókról.

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
