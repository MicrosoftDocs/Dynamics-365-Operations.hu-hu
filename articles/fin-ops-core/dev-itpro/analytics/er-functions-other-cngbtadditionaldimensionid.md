---
title: CN_GBT_ADDITIONALDIMENSIONID ER-függvény
description: A témakör tájékoztatást nyújt a CN_GBT_ADDITIONALDIMENSIONID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744391"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>CN_GBT_ADDITIONALDIMENSIONID ER-függvény

[!include [banner](../includes/banner.md)]

A `CN_GBT_ADDITIONALDIMENSIONID` függvény olyan *String* értéket ad vissza, amely egyetlen pénzügyi dimenzióazonosítót jelöl, amely a megadott karakterláncból származik. A megadott karakterlánc az összes dimenziót vesszővel tagolt azonosítólistaként jeleníti meg.

## <a name="syntax"></a>Szintaxis

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

A megadott *Karakterlánc* érték az összes dimenziót vesszővel tagolt azonosítólistaként jeleníti meg.

`number`: Egész

Az *Egész* érték a kért dimenzió számsorozatkódját határozza meg a megadott karakterláncban.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` a **"CC"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]