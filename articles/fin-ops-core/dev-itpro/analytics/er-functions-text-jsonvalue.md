---
title: JSONVALUE ER-függvény
description: A témakör tájékoztatást nyújt a JSONVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 11f9ac680ea00622367ea56106fd22508628d85d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685907"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `JSONVALUE` függvény elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítóval rendelkező skaláris érték kibontásához. Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket.

## <a name="syntax"></a>Szintaxis

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A JSON adatokat tartalmazó, *Karakterlánc* típusú adatforrás érvényes elérési útja.

`path`: *Karakterlánc*

A JSON adatok skaláris értékének azonosítója.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A **JsonField** adatforrás a következő adatokat tartalmazza JSON formátumban: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. Ebben az esetben a `JSONVALUE (JsonField, "BuildNumber")` kifejezés a következő *Karakterlánc* adattípusú értéket adja eredményül: **"7.3.1234.1"**.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
