---
title: ROUNDUP ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDUP Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
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
ms.openlocfilehash: 4898f596108ff3c563da55a567a10da987d62d33
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744439"
---
# <a name="roundup-er-function"></a>ROUNDUP ER-függvény

[!include [banner](../includes/banner.md)]

A `ROUNDUP` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre felfelé kerekítve.

## <a name="syntax"></a>Szintaxis

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Felfelé kerekítendő numerikus érték.

`decimals`: *Egész*

A tizedesjegyek számát jelölő numerikus érték.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig felfelé (nullával ellenkező irányba) kerekíti a megadott számot.

## <a name="example-1"></a>1. példa

A `ROUNDUP (1200.763, 2)` két tizedesjegyre kerekít fel, és az **1200.77** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `ROUNDUP (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít fel, és az **2000** értéket jeleníti meg.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]