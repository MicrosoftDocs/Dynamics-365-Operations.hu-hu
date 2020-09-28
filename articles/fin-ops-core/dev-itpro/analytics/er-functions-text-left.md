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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 112852ab955fdf8de9f78cc93486cc1d5f048517
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743783"
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
