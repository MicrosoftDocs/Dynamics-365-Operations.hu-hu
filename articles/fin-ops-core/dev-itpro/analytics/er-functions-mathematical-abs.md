---
title: ABS ER-függvény
description: Ez a cikk az ABS elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 90fbff223be5c195feb66b9ea72ee0688e60697b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886878"
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