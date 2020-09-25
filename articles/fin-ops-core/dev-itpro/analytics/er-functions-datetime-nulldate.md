---
title: NULLDATE ER-függvény
description: A témakör tájékoztatást nyújt a NULLDATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: edf43cc19636f51387504a7d9da73d757d96e558
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744287"
---
# <a name="nulldate-er-function"></a>NULLDATE ER-függvény

[!include [banner](../includes/banner.md)]

A `NULLDATE` függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli.

## <a name="syntax"></a>Szintaxis

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Visszaadott értékek

*Dátum*

Az eredményül kapott dátumérték.

## <a name="example-1"></a>1. példa

A `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` a **nulla** dátumot (1900. január 1.) adja vissza **"1900-01-01"** értékként, a megadott egyéni formátumban.

## <a name="example-2"></a>2. példa

Az `IF( Invoice.DocumentDate = NULLDATE(), true, false)` kifejezés **Igaz** értéket ad vissza, ha a **DocumentDate** mező értéke a **nulla** dátumnak felel meg. Ebben a példában a **Számla** a **Finance/Táblarekordok** típus Elektronikus jelentéskészítési (ER) adatforrása, és a CustInvoiceJour táblára hivatkozik.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
