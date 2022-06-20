---
title: NULLDATETIME ER-függvény
description: Ez a cikk a NULLDATETIME Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 3e8447d4f05ee8394842b9b07d14d1c054834bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867672"
---
# <a name="nulldatetime-er-function"></a>NULLDATETIME ER-függvény

[!include [banner](../includes/banner.md)]

A `NULLDATETIME` függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő (Greenwichi középidő \[GMT\]) formátumban.

## <a name="syntax"></a>Szintaxis

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="example"></a>Példa

A `DATETIMEFORMAT( NULLDATETIME(), "O")` az **1900-01-01T00:00:00.0000000+00:00** karakterláncértéket adja eredményül, amikor egy olyan folyamat során hívják meg, amelyet egy olyan alkalmazás kezdeményezett, amelynek a **Nyelvre és országra/régióra vonatkozó beállítások** szakaszában a **(GMT) Egyezményes Koordinált Világidő** érték van megadva.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]