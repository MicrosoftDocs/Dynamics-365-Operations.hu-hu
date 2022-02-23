---
title: SESSIONNOW ER-függvény
description: A témakör tájékoztatást nyújt a SESSIONNOW Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d70acb06194a28af0cc85eea440e9e4e937bc3bb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683843"
---
# <a name="sessionnow-er-function"></a>SESSIONNOW ER-függvény

[!include [banner](../includes/banner.md)]

A `SESSIONNOW` függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja.

## <a name="syntax"></a>Szintaxis

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="example"></a>Példa

A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
