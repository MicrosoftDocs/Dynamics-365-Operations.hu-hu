---
title: NEWGUID ER függvény
description: Ez a cikk a NEWGUID Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274772"
---
# <a name="newguid-er-function"></a>NEWGUID ER függvény

[!include [banner](../includes/banner.md)]

A `NEWGUID` függvény egy új globálisan egyedi azonosítót (GUID) hoz létre, és azt *[GUID](er-formula-supported-data-types-primitive.md#guid)* értékként adja vissza.

## <a name="syntax"></a>Szintaxis

```vb
NEWGUID ()
```

## <a name="return-values"></a>Visszatérési értékek

*GUID*

Az eredményül kapott GUID-érték.

## <a name="example"></a>Példa

A `NEWGUID()` mindig új *GUID*-értéket ad vissza, például **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
