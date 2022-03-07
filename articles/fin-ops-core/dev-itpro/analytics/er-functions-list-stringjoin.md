---
title: STRINGJOIN ER-függvény
description: A témakör tájékoztatást nyújt a STRINGJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 755e6481abb65dfecc8ddb6bceb032c8110095e2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568170"
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