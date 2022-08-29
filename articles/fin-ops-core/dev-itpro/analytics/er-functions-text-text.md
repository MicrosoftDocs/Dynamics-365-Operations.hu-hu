---
title: TEXT ER-függvény
description: Ez a cikk a TEXT Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: a32da5588c5231b20bc8166d20888c1611ca273e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278856"
---
# <a name="text-er-function"></a>TEXT ER-függvény

[!include [banner](../includes/banner.md)]

A `TEXT` függvény a megadott számot egy *Karakterlánc* értékként adja vissza, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja.

## <a name="syntax"></a>Szintaxis

```vb
TEXT (number)
```

## <a name="arguments"></a>Argumentumok

`number`: *Egész* vagy *Valós*

Olyan szám, amelyet szöveges karakterlánccá kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A *Valós* típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.

## <a name="example"></a>Példa

Microsoft Dynamics Ha a 365-ös **pénzügyi példány kiszolgálói területi értéke EN-US**, `TEXT (NOW ())` akkor az aktuális pénzügyi munkamenet 2015. december 17-ei dátumát adja vissza a **"12/17/2015 07:59:23 de" karakterláncként**. A `TEXT (1/3)` a **"0.33"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
