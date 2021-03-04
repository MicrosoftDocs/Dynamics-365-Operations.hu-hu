---
title: A lista kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott listafüggvényekről.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
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
ms.openlocfilehash: e2e708c59bceebf845ee78c98057133bb2892cf9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686176"
---
# <a name="list-of-er-functions-in-the-list-category"></a>A lista kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az elektronikus jelentés (ER) listafüggvényeivel kezelhetők a *Rekordlista* és a *Tároló (rekord)* adattípusok adatforrásai, és kinyerhetők belőlük adatok. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Ez a funkció a memóriában lévő kiválasztásként fut. Egy új, összevont *Rekordlista* értéket ad vissza, amely rekordok olyan listájából áll, amely a megadott útvonalnak megfelelő minden rekordot képvisel. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Ez a funkció illesztett SQL-lekérdezésként fut. Egy új, összevont *Rekordlista* értéket ad vissza, amely rekordok olyan listájából áll, amely a megadott útvonalnak megfelelő minden rekordot képvisel. |
| [Mennyiség](er-functions-list-count.md)                       | Ez a függvény egy *Egész* értéket ad eredményül, amely a megadott listában szereplő rekordok számát jelképezi, ha a lista nem üres. Ha a lista üres, a függvény **0** (nulla) értéket ad vissza. |
| [EmptyList](er-functions-list-emptylist.md)               | Ez a függvény a megadott lista forrásként való felhasználásával egy üres *Rekordlista* értéket ad vissza a lista szerkezetére vonatkozó forrásként.|
| [Enumerálás](er-functions-list-enumerate.md)               | Ez a függvény egy új *Rekordlista* értéket ad vissza, amely a megadott lista felsorolt rekordjaiból áll. |
| [Szűrés](er-functions-list-filter.md)                     | Ez a függvény a megadott listát egy *Rekordlista* értékként adja vissza, miután a lekérdezés módosult, és a megadott feltételt szűri. |
| [Első](er-functions-list-first.md)                       | Ez a függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a lista nem üres. Ha a lista üres, a függvény kivételt dob. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Ez a függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres. Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza. |
| [Index](er-functions-list-index.md)                       | Ez a függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott numerikus index használatával került kiválasztásra a megadott listában. Ha az index kívül esik a listán megadott rekordok tartományán, akkor a függvény kivételt dob. |
| [IsEmpty](er-functions-list-isempty.md)                   | Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott lista nem tartalmaz rekordokat. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [Lista](er-functions-list-list.md)                         | Ez a függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új listából áll.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Ez a funkció kiszámítja a megadott kifejezéseket, mint egy választót minden rekordra a megadott listában. Ez visszaállít egy új *Rekordlista* értéket, amely egyetlen rekordot tartalmaz minden egyedi választóértékhez.|
| [ListJoin](er-functions-list-listjoin.md)                 | Ez a függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új listát jeleníti meg.|
| [ListOfFields](er-functions-list-listoffields.md)         | Ez a függvény egy *Rekordlista* értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus megadott argumentumának szerkezete alapján jön létre. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Ez a függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.|
| [OrderBy](er-functions-list-orderby.md)                   | Ez a függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott argumentumok szerint rendezésre került. Ezek az argumentumok kifejezésként adhatók meg. |
| [Megfordítás](er-functions-list-reverse.md)                   | Ez a függvény a megadott listát *Rekordlista* értékként adja vissza fordított rendezési sorrendben. |
| [Megosztás](er-functions-list-split.md)                       | Ez a függvény az adott bemeneti karakterláncot alkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza. |
| [SplitList](er-functions-list-splitlist.md)               | Ez a függvény a megadott listát allistákká (vagy kötegekké) osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz. Ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Ez a függvény a megadott listát az allisták (kötegek) új listájára osztja fel. Az egyes kötegekben lévő rekordok számát dinamikusan számítja a rendszer. A függvény ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll. |
| [StringJoin](er-functions-list-stringjoin.md)             | Ez a függvény egy *Karakterlánc* értéket ad vissza, amely a megadott lista megadott mezőjének összefűzött értékeiből áll. Az értékeket a megadott elválasztó elválaszthatja egymástól. |
| [Ahol](er-functions-list-where.md)                       | Ez a függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott feltételek szerint szűrésre került. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]