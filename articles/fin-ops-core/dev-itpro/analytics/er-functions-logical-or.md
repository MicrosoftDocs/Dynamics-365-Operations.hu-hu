---
title: OR ER-függvény
description: A témakör tájékoztatást nyújt az OR Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747569"
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