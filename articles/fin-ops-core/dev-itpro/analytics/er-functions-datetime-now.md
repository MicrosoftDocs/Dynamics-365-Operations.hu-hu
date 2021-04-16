---
title: NOW ER-függvény
description: A témakör tájékoztatást nyújt a NOW Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746867"
---
# <a name="now-er-function"></a>NOW ER-függvény

[!include [banner](../includes/banner.md)]

A `NOW` függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja.

## <a name="syntax"></a>Szintaxis

```vb
NOW ()
```

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="example"></a>Példa

A `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátum-/időértékét, a 2015. december 24-et adja vissza **"24-12-2015"** formában, a megadott egyéni formátum szerint.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]