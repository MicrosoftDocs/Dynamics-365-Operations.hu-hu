---
title: STRINGJOIN ER-függvény
description: A témakör tájékoztatást nyújt a STRINGJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: ac21651e0f5b5a1579b9335bb7f3217370c4d5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745521"
---
# <a name="stringjoin-er-function"></a>STRINGJOIN ER-függvény

[!include [banner](../includes/banner.md)]

A `STRINGJOIN` függvény egy *Karakterlánc* értéket ad vissza, amely a megadott lista megadott mezőjének összefűzött értékeiből áll. Az értékeket a megadott elválasztó elválaszthatja egymástól.

## <a name="syntax"></a>Szintaxis

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`field`: *Mező*

A *Karakterlánc* adattípusú mezők érvényes elérési útja a megadott listában.

`delimiter`: *Karakterlánc*

A részkarakterláncok elválasztására használt határolójel.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

Ha megadja a `SPLIT("abc" , 1)` kifejezést **DS** adatforrásként, akkor a `STRINGJOIN (DS, DS.Value, "-")` kifejezés az **"a-b-c"** értéket adja eredményül.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]