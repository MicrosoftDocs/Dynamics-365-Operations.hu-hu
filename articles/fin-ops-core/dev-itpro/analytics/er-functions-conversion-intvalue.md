---
title: INTVALUE ER-függvény
description: A témakör tájékoztatást nyújt az INTVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743639"
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
