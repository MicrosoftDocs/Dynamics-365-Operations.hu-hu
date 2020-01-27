---
title: INT64VALUE ER-függvény
description: A témakör tájékoztatást nyújt a INT64VALUE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 75df802b75454baeea75a8ceb32d5d045a77a3a0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916545"
---
# <a name="INT64VALUE">INT64VALUE ER-függvény</a>

[!include [banner](../includes/banner.md)]

Az `INT64VALUE` függvény a megadott karakterláncot jelölő *Int64* értéket ad vissza.

## <a name="syntax-1"></a>Szintaxis 1

```
INT64VALUE (text)
```

## <a name="syntax-2"></a>Szintaxis 2

```
INT64VALUE (number)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy szöveges érték, amelyet *Int64* számmá kell konvertálni.

`number`: *Valós* vagy *Egész*

Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int64* számmá kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Int64*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Minden tizedesjegy csonkolásra kerül.

## <a name="example-1"></a>1. példa

Az `INT64VALUE ("22565422744")` az *Int64* esetében a **22565422744** értéket adja vissza.

## <a name="example-2"></a>2. példa

Az `INT64VALUE ( VALUE("22565422744.77"))` az *Int64* esetében a **22565422744** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Típuskonverziós függvények](er-functions-category-type-conversion.md)
