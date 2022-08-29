---
title: ROUND ER-függvény
description: Ez a cikk a ROUND Electronic Reporting (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 57d41ed92a5577fdc5fffeccef2834e9b6fb5197
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286059"
---
# <a name="round-er-function"></a>ROUND ER-függvény

[!include [banner](../includes/banner.md)]

A `ROUND` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre kerekítve.

## <a name="syntax"></a>Szintaxis

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Kerekítendő numerikus érték.

`decimals`: *Egész*

A tizedesjegyek számát jelölő numerikus érték.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a megadott `decimals` argumentum értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek ezen megadott számára van kerekítve.

Ha a `decimals` argumentum értéke **0** (nulla), a megadott szám a legközelebbi páros egészre van kerekítve.

Ha a `decimals` argumentum értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesvessző bal oldalára van kerekítve.

## <a name="example-1"></a>1. példa

A `ROUND (1200.767, 2)` két tizedesjegyre kerekít és a **1200.77** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `ROUND (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít és az **1000** értéket jelenít meg.

## <a name="example-3"></a>3. példa

`ROUND (1200.5, 0)` kerekít a legközelebbi páros egész számra, és **1200**-at ad vissza, míg a `ROUND (1201.5, 0)` ugyanezt teszi, és **1202**-t ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Matematikai függvények](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
