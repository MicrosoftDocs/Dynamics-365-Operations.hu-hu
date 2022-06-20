---
title: ISVALIDCHARACTERISO7064 ER-függvény
description: Ez a cikk az ISVALIDCHARACTERISO7064 Electronic reporting (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 43da66e79bd8fbeecf5a04283574077600552a05
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908474"
---
# <a name="isvalidcharacteriso7064-er-function"></a>ISVALIDCHARACTERISO7064 ER-függvény

[!include [banner](../includes/banner.md)]

A `ISVALIDCHARACTERISO7064` függvény *logikai* **IGAZ** értéket ad vissza, ha a megadott karakterlánc érvényes nemzetközi bankszámlaszámnak (IBAN) felel meg. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy IBAN értéket képviselő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

Az `ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` **IGAZ** értéket ad vissza. 

Az `ISVALIDCHARACTERISO7064 ("AT61")` **HAMIS** értéket ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]