---
title: OR ER-függvény
description: Ez a cikk az OR Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: d2783b5aff34e6ab4b5bde5dfe39e92d20892634
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892951"
---
# <a name="or-er-function"></a>OR ER-függvény

[!include [banner](../includes/banner.md)]

Az `OR` függvény **HAMIS** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike hamis. Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek bármelyike igaz.

## <a name="syntax"></a>Szintaxis

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentumok

`condition 1`: *Logikai*

Érvényes feltételes kifejezés, amelyet tesztelni kell. Az argumentum megadása kötelező.

`condition N`: *Logikai*

Érvényes feltételes kifejezés, amelyet tesztelni kell. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="example"></a>Példa

Az `OR (1=2, "a"="a")` **IGAZ** értéket ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]