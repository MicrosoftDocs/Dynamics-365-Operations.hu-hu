---
title: A dátum és időpont kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott dátum és időpont függvényekről.
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
ms.openlocfilehash: 0a0322e5490474e21ad91076ecc486f38a776e32
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7890777"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>A dátum és időpont kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) dátum és időpont függvényeinek segítségével adatokat nyerhet ki a dátum-és időértékekből, és műveleteket hajthat végre rajtuk. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Ez a függvény egy *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* értéket ad eredményül, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum/idő értékről egy időzónába n átváltásra kerül egy dátum/idő értékre egy másik időzónában. |
| [DateFormat](er-functions-datetime-dateformat.md) | Ez a függvény egy *[Sztring](er-formula-supported-data-types-primitive.md#string)* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban. |
| [DateValue](er-functions-datetime-datevalue.md) | Ez a funkció olyan dátumértéket ad vissza, amely a megadott formátumban és tetszés szerint megadott kulturális környezetben megadott szövegértékből *[...](er-formula-supported-data-types-primitive.md#date)* dátumértékké alakul át. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Ez a függvény egy egész számot ad vissza, amely a január 1. és a megadott dátum közötti *[napok számának megfelelő értéket](er-formula-supported-data-types-primitive.md#integer)* ad vissza. |
| [nap](er-functions-datetime-days.md) | Ez a függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja. |
| [Now](er-functions-datetime-now.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja. |
| [NullDate](er-functions-datetime-nulldate.md) | Ez a függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli. |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő formátumban. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja. |
| [Ma](er-functions-datetime-today.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja. |
| [Hét száma](er-functions-datetime-weeknum.md) | Ez a függvény az év hetének megfelelő egész értéket *ad* eredményül. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
