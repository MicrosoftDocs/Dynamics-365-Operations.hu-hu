---
title: ADDDAYS ER-függvény
description: Ez a cikk az ADDDAYS Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 69273794def0dc52dc8e31615c319ccf5067fa77
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274139"
---
# <a name="adddays-er-function"></a>ADDDAYS ER-függvény

[!include [banner](../includes/banner.md)]

Az `ADDDAYS` függvény egy *DateTime* értéket számít ki, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van.

## <a name="syntax"></a>Szintaxis

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumentumok

`datetime`: *DateTime*

A kezdő dátumot reprezentáló dátum-/időérték.

`days`: *Egész*

A `datetime` előtti vagy utáni napok száma.

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="usage-notes"></a>Használati megjegyzések

A `days` pozitív értéke egy jövőbeli dátumot eredményez. A negatív érték egy múltbeli dátumot eredményez.

## <a name="example-1"></a>1. példa

Az `ADDDAYS (NOW(), 7)` megjeleníti a hét nappal későbbi dátumot és időpontot.

## <a name="example-2"></a>2. példa

Az `ADDDAYS (NOW(), -3)` megjeleníti a három nappal korábbi dátumot és időpontot.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
