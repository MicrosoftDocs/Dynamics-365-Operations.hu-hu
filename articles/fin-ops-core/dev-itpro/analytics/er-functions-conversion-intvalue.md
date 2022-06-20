---
title: INTVALUE ER-függvény
description: Ez a cikk az INTVALUE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: e2357541f922ad9af5c5ce342d0e7d89e8709734
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879891"
---
# <a name="intvalue-er-function"></a>INTVALUE ER-függvény

[!include [banner](../includes/banner.md)]

Az `INTVALUE` függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.

## <a name="syntax-1"></a>Szintaxis 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy szöveges érték, amelyet *Int* számmá kell konvertálni.

`number`: *Valós* vagy *Egész*

Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int* számmá kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Int*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Minden tizedesjegy csonkolásra kerül.

## <a name="example-1"></a>1. példa

Az `INTVALUE ("100.77")` az *Int* esetében a **100** értéket adja vissza.

## <a name="example-2"></a>2. példa

Az `INTVALUE (-100.77)` az *Int* esetében a **-100** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Típuskonverziós függvények](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]