---
title: CN_GBT_ADDITIONALDIMENSIONID ER-függvény
description: A témakör tájékoztatást nyújt a CN_GBT_ADDITIONALDIMENSIONID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 38908c63c35465747505479bc983ada891f9e2bf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686810"
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
