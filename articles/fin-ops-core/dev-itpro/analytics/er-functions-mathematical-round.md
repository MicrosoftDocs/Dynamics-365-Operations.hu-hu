---
title: ROUND ER-függvény
description: A témakör tájékoztatást nyújt a ROUND Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c9384d5975e4a25d18ff741f87431daa4b0bbd7e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917074"
---
# <a name="ROUND">ROUND ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `ROUND` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre kerekítve.

## <a name="syntax"></a>Szintaxis

```
ROUND (number, decimals)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Kerekítendő numerikus érték.

`decimals`: *Egész*

A tizedesjegyek számát jelölő numerikus érték.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a megadott `decimals` argumentum értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek ezen megadott számára van kerekítve.

Ha a `decimals` argumentum értéke **0** (nulla), a megadott szám a legközelebbi egészre van kerekítve.

Ha a `decimals` argumentum értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesvessző bal oldalára van kerekítve.

## <a name="example-1"></a>1. példa

A `ROUND (1200.767, 2)` két tizedesjegyre kerekít és a **1200.77** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `ROUND (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít és az **1000** értéket jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)
