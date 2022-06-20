---
title: A dátum és időpont kategóriába tartozó ER-függvények listája
description: Ez a cikk az elektronikus jelentéskészítés (ER) által támogatott dátum- és időfunkciókról nyújt tájékoztatást.
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: e6e15d143bad016883f03ecf0125ce9429215a71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880239"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>A dátum és időpont kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) dátum és időpont függvényeinek segítségével adatokat nyerhet ki a dátum-és időértékekből, és műveleteket hajthat végre rajtuk. Ez a témakör összefoglalást nyújt a funkciókról.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Ez a függvény egy *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* értéket ad eredményül, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum/idő értékről egy időzónába n átváltásra kerül egy dátum/idő értékre egy másik időzónában. |
| [DateFormat](er-functions-datetime-dateformat.md) | Ez a függvény egy *[Sztring](er-formula-supported-data-types-primitive.md#string)* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban. |
| [DateValue](er-functions-datetime-datevalue.md) | Ez a funkció olyan dátumértéket *[ad](er-formula-supported-data-types-primitive.md#date)* vissza, amely a megadott formátumban és tetszés szerint megadott kulturális környezetben megadott szövegértékből dátumértékké alakul át. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Ez a függvény egy *[egész](er-formula-supported-data-types-primitive.md#integer)* számot ad vissza, amely a január 1. és a megadott dátum közötti napok számának megfelelő értéket ad vissza. |
| [nap](er-functions-datetime-days.md) | Ez a függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja. |
| [Now](er-functions-datetime-now.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja. |
| [NullDate](er-functions-datetime-nulldate.md) | Ez a függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli. |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő formátumban. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja. |
| [Ma](er-functions-datetime-today.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja. |
| [WeekNum](er-functions-datetime-weeknum.md) | Ez a függvény az *év* hetének megfelelő egész értéket ad eredményül. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
