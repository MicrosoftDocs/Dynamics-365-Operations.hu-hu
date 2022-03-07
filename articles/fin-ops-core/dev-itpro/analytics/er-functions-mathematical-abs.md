---
title: ABS ER-függvény
description: A témakör tájékoztatást nyújt az ABS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: db12ddddb087556414e81d646c4c87d273a77c133e49152091452d0731916e93
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776074"
---
# <a name="abs-er-function"></a>ABS ER-függvény

[!include [banner](../includes/banner.md)]

Az `ABS` függvény a megadott szám abszolútértékét (modulus) adja eredményül *Valós* értékként. Más szóval, a számot előjel nélkül adja vissza.

## <a name="syntax"></a>Szintaxis

```vb
ABS (number)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Egy numerikus érték, amelynek a modulus értékét meg szeretné jeleníteni.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="example"></a>Példa

Az `ABS (-1)` az **1** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]