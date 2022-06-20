---
title: NUMBERVALUE ER-függvény
description: Ez a cikk a NUMBERVALUE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 9701fe7a1ce2a96fa5fa8df8aeda125c861a117a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871527"
---
# <a name="numbervalue-er-function"></a>NUMBERVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `NUMBERVALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át. Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni.

## <a name="syntax"></a>Szintaxis

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy szöveges érték, amelyet *Valós* számmá kell konvertálni.

`decimal separator`: Karakterlánc

Tizedeselválasztó. A decimális számok egész és tört részeinek elválasztására szolgál.

`digit grouping separator`: *Karakterlánc*

Számjegy-csoportosító elválasztó. Ezreselválasztóként használják.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="example"></a>Példa

A `NUMBERVALUE( "1 234,56", ",", " ")` az **1234,56** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Típuskonverziós függvények](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]