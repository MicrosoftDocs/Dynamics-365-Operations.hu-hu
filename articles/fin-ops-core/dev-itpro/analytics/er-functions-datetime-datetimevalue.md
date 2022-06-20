---
title: DATETIMEVALUE ER-függvény
description: Ez a cikk a DATETIMEVALUE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 7e3af6a279163183546255908730ba32d790a22b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870435"
---
# <a name="datetimevalue-er-function"></a>DATETIMEVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `DATETIMEVALUE` függvény egy *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható [területi beállításban](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) egy dátum/idő értékre. A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](/dotnet/standard/base-types/standard-date-and-time-format-strings) és [egyéni](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Szintaxis 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumentumok

`text`: *[Sztring](er-formula-supported-data-types-primitive.md#string)*

A formázni kívánt értéket reprezentáló szöveg.

`format`: *Karakterlánc*

Az adott szöveg formátuma. A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](/dotnet/standard/base-types/standard-date-and-time-format-strings) és [egyéni](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Karakterlánc*

A megadott szöveg formázásához használt területi beállítás. További tájékoztatás a támogatott kulturális környezetről: [Kulturális környezet](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Visszatérési értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg. Ha például a `DATETIMEVALUE` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német kultúra használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német kultúra használatával történik. Az alapértelmezett `culture` érték **EN-US**.

## <a name="example-1"></a>1. példa

A `DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` a **2:55:00 AM on December 21, 2016** dátumértéket adja vissza a megadott egyéni formátum szerint, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint.

## <a name="example-2"></a>2. példa

A `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` a **2:55:00 am december 21, 2016** értéket adja vissza a megadott egyéni formátum és területi beállítás.

A `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` viszont kivételt dob, hogy tájékoztassa a felhasználót arról, hogy a megadott karakterlánc nem ismerhető fel a megadott területi beállítások érvényes dátum-/időértékeként.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
