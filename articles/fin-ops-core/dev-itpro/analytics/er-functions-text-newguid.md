---
title: NEWGUID ER függvény
description: Ez a cikk a NEWGUID Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 321e2eda4accf9c8fe33b5a4c092c7be55276f26
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861816"
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
