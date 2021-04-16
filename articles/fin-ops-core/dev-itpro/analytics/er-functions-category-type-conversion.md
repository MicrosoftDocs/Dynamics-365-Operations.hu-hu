---
title: A típuskonverzió kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott konverziós függvényekről.
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
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
ms.openlocfilehash: 199d51ae8a4dbdd7d2f3bd290a2b487ceb1174dc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752604"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>A típuskonverzió kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) típuskonverziós függvényei az értékek típusok közötti konvertálására használhatók. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="type-conversion-functions"></a>Típuskonverziós függvények

| Funkció | Leírás |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Ez a függvény a megadott karakterláncot jelölő *Int64* értéket ad vissza. |
| [IntValue](er-functions-conversion-intvalue.md)       | Ez a függvény a megadott karakterláncot jelölő *Int* értéket ad vissza. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át. Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni. |
| [Érték](er-functions-conversion-value.md)             | Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át. |

## <a name="type-conversion-functions-in-the-container-category"></a>A tároló kategória típuskonverziós függvényei

A következő táblázat a [tároló](er-functions-category-container.md) kategória típuskonverziós függvényeit ismerteti.

| Függvény | Leírás |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Ez a függvény a megadott *Karakterlánc* típusú bemenetet *Tároló* típusú adatelemmé konvertálja. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Típuskonverziós függvények a dátum és időpont kategóriában

A következő táblázat a [dátum és időpont kategória](er-functions-category-datetime.md) típuskonverziós függvényeit ismerteti.

| Funkció | Leírás |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott *Dátum* értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban. |
| [DateValue](er-functions-datetime-datevalue.md)           | Ez a függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum értékre. |

## <a name="type-conversion-functions-in-the-list-category"></a>A lista kategória típuskonverziós függvényei

A következő táblázat a [lista kategória](er-functions-category-list.md) típuskonverziós függvényeit ismerteti.

| Funkció | Leírás |
|----------|-------------|
| [Lista](er-functions-list-list.md)                 | Ez a függvény egy *Rekordlista* értéket ad vissza a *Tároló (rekord)* típus megadott argumentumaiból létrehozott új listaként. |
| [ListOfFields](er-functions-list-listoffields.md) | Ez a függvény egy *Rekordlista* értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus egy adott argumentumának szerkezete alapján jön létre. |
| [Megosztás](er-functions-list-split.md)               | Ez a függvény az adott *Karakterlánc* értéket alkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza. |
| [StringJoin](er-functions-list-stringjoin.md)     | Ez a függvény egy *Karakterlánc* értéket ad vissza, amely a megadott *Rekordlista* érték megadott mezőjének összefűzött értékeiből áll. Az értékeket a megadott elválasztó elválaszthatja egymástól. |

## <a name="type-conversion-functions-in-the-text-category"></a>A szöveg kategória típuskonverziós függvényei

A következő táblázat a [szöveg kategória](er-functions-category-text.md) típuskonverziós függvényeit ismerteti.

| Funkció | Leírás |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Ez a függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik. |
| [GuidValue](er-functions-text-guidvalue.md)       | Ez a függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja. |
| [NumberFormat](er-functions-text-numberformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [QrCode](er-functions-text-qrcode.md)             | Ez a függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód). |
| [Szöveg](er-functions-text-text.md)                 | A függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számot jelzi, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]