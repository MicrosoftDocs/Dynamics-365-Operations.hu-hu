---
title: TODAY ER-függvény
description: A témakör tájékoztatást nyújt a TODAY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: a93a9171456fb69e16c8104b0afb9ad485311b1a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683795"
---
# <a name="today-er-function"></a>TODAY ER-függvény

[!include [banner](../includes/banner.md)]

A `TODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja.

## <a name="syntax"></a>Szintaxis

```xpp
TODAY ()
```

## <a name="return-values"></a>Visszaadott értékek

*Dátum*

Az eredményül kapott dátumérték.

## <a name="example"></a>Példa

A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]