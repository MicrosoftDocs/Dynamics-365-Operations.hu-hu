---
title: ADDDAYS ER-függvény
description: Ez a cikk az ADDDAYS Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 7cf2031c042ae93512cc85afe6a1b51558f6c8f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858741"
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