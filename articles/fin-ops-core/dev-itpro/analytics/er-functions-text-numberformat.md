---
title: NUMBERFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a NUMBERFORMAT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a431414044846bf4e79e6b9f0e5b27281ea8f46
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744407"
---
# <a name="numberformat-er-function"></a>NUMBERFORMAT ER-függvény

[!include [banner](../includes/banner.md)]

A `NUMBERFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállítással](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

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
