---
title: MOD_97 ER-függvény
description: A témakör tájékoztatást nyújt a MOD_97 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: ce2192c7bc849996e08573d71d8ed43956c8fb89
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070529"
---
# <a name="MOD_97">MOD_97 ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `MOD_97` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD97-kifejezésként jelöli, a megadott számlaszám számjegyei alapján.

## <a name="syntax"></a>Szintaxis

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argumentumok

`invoice number digits`: *Karakterlánc*

A számlaszámok számjegyeit jelölő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `MOD_97 ("VEND-200002")` a **"20000285"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)
