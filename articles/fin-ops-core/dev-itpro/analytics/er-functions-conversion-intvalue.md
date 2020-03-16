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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042650"
---
# <a name="INTVALUE">INTVALUE ER-függvény</a>

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
