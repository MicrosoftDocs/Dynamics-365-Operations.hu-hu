---
title: NEWGUID ER függvény
description: A témakör tájékoztatást nyújt a NEWGUID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 5856a4d765f5136ecb11a34e0255c1ba88818f2c
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647938"
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
