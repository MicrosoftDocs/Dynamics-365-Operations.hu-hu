---
title: CURCREDREF ER-függvény
description: A témakör tájékoztatást nyújt a CURCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: c90385c3bf64adfe80fa054e1eb78a6aa368c04eb1758a2e453669bb3d4b7214
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727509"
---
# <a name="curcredref-er-function"></a>CURCREDREF ER-függvény

[!include [banner](../includes/banner.md)]

A `CURCREDREF` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást képviseli a megadott számlaszám számjegyei alapján.

## <a name="syntax"></a>Szintaxis

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumentumok

`invoice number digits`: *Karakterlánc*

A számlaszámok számjegyeit jelölő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `CURCredRef ("VEND-200002")` a **"2200002"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]