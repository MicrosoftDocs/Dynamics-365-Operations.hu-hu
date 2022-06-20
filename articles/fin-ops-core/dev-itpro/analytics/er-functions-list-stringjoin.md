---
title: STRINGJOIN ER-függvény
description: Ez a cikk a STRINGJOIN Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 08ed76f4dc61ed8afd63ffe99cead4866b63aba9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908503"
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