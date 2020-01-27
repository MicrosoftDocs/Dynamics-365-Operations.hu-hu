---
title: DAYOFYEAR ER-függvény
description: A témakör tájékoztatást nyújt a DAYOFYEAR Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1080a1c2e30cd7ca64ea43120c11eb90d3c99416
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916338"
---
# <a name="DAYOFYEAR">DAYOFYEAR ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `DAYOFYEAR` függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.

## <a name="syntax"></a>Szintaxis

```
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argumentumok

`date`: *Dátum*

A napok számának kiszámításához használandó dátumot jelképező dátumérték.

## <a name="return-values"></a>Visszaadott értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="example-1"></a>1. példa

A `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` a **61** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` az **1** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
