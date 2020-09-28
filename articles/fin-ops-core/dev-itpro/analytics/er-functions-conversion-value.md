---
title: VALUE ER-függvény
description: A témakör tájékoztatást nyújt a VALUE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ecbffb7e39d7f2f2bccdfe32d593512a65da163c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745513"
---
# <a name="value-er-function"></a>VALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `VALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott karakterláncból alakít át.

## <a name="syntax"></a>Szintaxis

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy karakterlánc érték, amelyet numerikus értékké kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál. Kivételt ad futási időben, ha más nem numerikus karakterek találhatók a megadott karakterláncban.

## <a name="example-1"></a>1. példa

A `VALUE ("1 234,56")` kivételt dob.

## <a name="example-2"></a>2. példa

A `VALUE ("1234,56")` az **1234.56** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Típuskonverziós függvények](er-functions-category-type-conversion.md)
