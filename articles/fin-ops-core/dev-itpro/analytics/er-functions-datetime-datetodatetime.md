---
title: DATETODATETIME ER-függvény
description: A témakör tájékoztatást nyújt a DATETODATETIME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5ad1d304f0914a9ddbca951cdb7419dbcc1f46
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682439"
---
# <a name="datetodatetime-er-function"></a>DATETODATETIME ER-függvény

[!include [banner](../includes/banner.md)]

A `DATETODATETIME` függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban.

## <a name="syntax"></a>Szintaxis

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argumentumok

`date`: *Dátum*

Az átalakítani kívánt dátumot reprezentáló dátumérték.

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="example-1"></a>1. példa

A `DATETODATETIME (CompInfo. 'getCurrentDate()')` a jelenlegi Microsoft Dynamics 365 Finance munkamenet dátumát (2015. december 24.) adja vissza **12/24/2015 12:00:00 AM** értékként. Ebben a példában a **CompInfo** a **Finance and Operations/Tábla** típus Elektronikus jelentéskészítési (ER) adatforrása, és a CompanyInfo táblára hivatkozik.

## <a name="example-2"></a>2. példa

A `DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` a **11/12/2019 12:00:00 AM** dátum-/időértéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
