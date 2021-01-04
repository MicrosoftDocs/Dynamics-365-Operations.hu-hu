---
title: A dátum és időpont kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott dátum és időpont függvényekről.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2745298ae1f6787c3de5a4aaf6a2a6350f5f3e85
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686219"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>A dátum és időpont kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) dátum és időpont függvényeinek segítségével adatokat nyerhet ki a dátum-és időértékekből, és műveleteket hajthat végre rajtuk. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van. |
| [DateFormat](er-functions-datetime-dateformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban. |
| [DateValue](er-functions-datetime-datevalue.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátumértékre. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Ez a függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja. |
| [nap](er-functions-datetime-days.md) | Ez a függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja. |
| [Now](er-functions-datetime-now.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja. |
| [NullDate](er-functions-datetime-nulldate.md) | Ez a függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli. |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő formátumban. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja. |
| [Ma](er-functions-datetime-today.md) | Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
