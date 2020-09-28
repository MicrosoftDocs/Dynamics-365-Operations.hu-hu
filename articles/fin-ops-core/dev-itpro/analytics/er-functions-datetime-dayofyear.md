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
ms.openlocfilehash: 755f5f1de28f95ed682648caf47155ad71c8f4b0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745489"
---
# <a name="dayofyear-er-function"></a>DAYOFYEAR ER-függvény

[!include [banner](../includes/banner.md)]

A `DAYOFYEAR` függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.

## <a name="syntax"></a>Szintaxis

```vb
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
