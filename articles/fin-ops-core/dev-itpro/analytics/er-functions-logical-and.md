---
title: AND ER-függvény
description: A témakör tájékoztatást nyújt az AND Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 068b9a3b2cf2e5bffe895bc4e8a7cbb2d8025ad7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560085"
---
# <a name="and-er-function"></a>AND ER-függvény

[!include [banner](../includes/banner.md)]

Az `AND` függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike igaz. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentumok

`condition 1`: *Logikai*

Érvényes feltételes kifejezés, amelyet tesztelni kell. Az argumentum megadása kötelező.

`condition N`: *Logikai*

Érvényes feltételes kifejezés, amelyet tesztelni kell. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="usage-notes"></a>Használati megjegyzések

A logikai függvények argumentumaiban az adatforrás-hivatkozások, a numerikus és szöveges értékek, a logikai értékek, az összehasonlító operátorok és más Elektronikus jelentéskészítési (ER) függvények használhatók. Azonban az összes argumentumot **IGAZ** vagy **HAMIS** *logikai* értékre kell értékelni.

## <a name="example"></a>Példa

Az `AND (1=1, "a"="a")` **IGAZ** értéket ad vissza.

Az `AND (1=2, "a"="a")` **HAMIS** értéket ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]