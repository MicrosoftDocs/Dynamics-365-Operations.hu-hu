---
title: VALUE ER-függvény
description: Ez a cikk az VALUE Electronic Reporting (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 0a47637c47ca6c947451efa1230191779401b4e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277662"
---
# <a name="value-er-function"></a>VALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `VALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott karakterláncból alakít át.

## <a name="syntax"></a>Szintaxis

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy karakterlánc érték, amelyet numerikus értékké kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál. Kivételt ad futási időben, ha más nem numerikus karakterek találhatók a megadott karakterláncban.

## <a name="example-1"></a>1. példa

A `VALUE ("1 234,56")` kivételt dob.

## <a name="example-2"></a>2. példa

A `VALUE ("1234,56")` az **1234.56** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Típuskonverziós függvények](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
