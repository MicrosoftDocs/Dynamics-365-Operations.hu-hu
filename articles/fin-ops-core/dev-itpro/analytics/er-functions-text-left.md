---
title: LEFT ER-függvény
description: A témakör tájékoztatást nyújt a LEFT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 9e9cdff9bb5c22c74803cf17c056c0ff1af5ef43
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685883"
---
# <a name="left-er-function"></a>LEFT ER-függvény

[!include [banner](../includes/banner.md)]

A `LEFT` függvény olyan *String* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után.

## <a name="syntax"></a>Szintaxis

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Az eredeti szöveget jelölő *Karakterlánc* érték.

`number`: *Egész*

Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg kezdetétől.

## <a name="return-values"></a>Visszatérési értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `LEFT ("Sample", 3)` a **"Sam"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
