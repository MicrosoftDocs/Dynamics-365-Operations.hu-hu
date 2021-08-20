---
title: NUMBERFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a NUMBERFORMAT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0208796382bd6564539ebbe3d902cc41dedce235adafefe1126961774cdb2076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749728"
---
# <a name="numberformat-er-function"></a>NUMBERFORMAT ER-függvény

[!include [banner](../includes/banner.md)]

A `NUMBERFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállítással](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](/dotnet/standard/base-types/standard-numeric-format-strings) és [egyéni](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="syntax-1"></a>Szintaxis 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argumentumok

`number`: *Egész* vagy *Valós*

Egy numerikus érték, amely megadja a formázandó számot.

`format`: *Karakterlánc*

A formátumot jelölő *Karakterlánc* érték.

`culture`: *Karakterlánc*

*Karakterlánc* érték, amely a formázáshoz használandó területi beállítást jelöli.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a területi beállítás nem a hívott függvény argumentumaként van definiálva, a függvény által futtatott környezet határozza meg a számok formázásához használt területi beállítást.

## <a name="example-1"></a>1. példa

Az **EN-US** területi beállítás esetében a `NUMBERFORMAT (0.45, "p")` a **"45.00 %"** értéket, a `NUMBERFORMAT (10.45, "#")` pedig a **"10"** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `NUMBERFORMAT (10/3, "F2", "de")` a **3,33** értéket adja vissza, míg a `NUMBERFORMAT (10/3, "F2", "en-us")` a **3.33** értéket.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]