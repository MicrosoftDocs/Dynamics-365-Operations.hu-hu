---
title: FIRSTORNULL ER függvény
description: Ez a cikk bemutatja a FIRSTORLL elektronikus jelentéskészítő (ER) funkció működését.
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: bae2916371cd00810f559ff2006b2b238c8ad918
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900251"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL ER függvény

[!include [banner](../includes/banner.md)]

A `FIRSTORNULL` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres. Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza.

## <a name="syntax"></a>Szintaxis

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example"></a>Példa

A `FIRSTORNULL(SPLIT("",1)).Value` kifejezés üres karakterláncot ad eredményül (**""**).

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]