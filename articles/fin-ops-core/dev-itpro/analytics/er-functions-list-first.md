---
title: FIRST ER-függvény
description: Ez a cikk a FIRST Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: a1f841fe11f025be95ffee2750da74ad7be51624
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906576"
---
# <a name="first-er-function"></a>FIRST ER-függvény

[!include [banner](../includes/banner.md)]

A `FIRST` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a lista nem üres. Ha a lista üres, a függvény kivételt dob.

## <a name="syntax"></a>Szintaxis

```vb
FIRST (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example-1"></a>1. példa

Az `FIRST(SPLIT("ABC",1)).Value` kifejezés az **„A”** szöveges értéket adja eredményül.

## <a name="example-2"></a>2. példa

A `FIRST(SPLIT("",1)).Value` kifejezés futásidőben kivételt dob.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]