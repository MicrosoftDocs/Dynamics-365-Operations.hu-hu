---
title: ROUNDDOWN ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDDOWN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 7ac559983609d4fdb80c9ac70d84031e4a231889
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744527"
---
# <a name="rounddown-er-function"></a>ROUNDDOWN ER-függvény

[!include [banner](../includes/banner.md)]

A `ROUNDDOWN` funkció a megadott számot adja vissza *Valós* értékként, lefelé kerekítve adott számú tizedesjegyre.

## <a name="syntax"></a>Szintaxis

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Lefelé kerekítendő numerikus érték.

`decimals`: *Egész*

A tizedesjegyek számát jelölő numerikus érték.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig lefelé (nulla felé) kerekíti a megadott számot.

## <a name="example-1"></a>1. példa

A `ROUNDDOWN (1200.767, 2)` két tizedesjegyre kerekít lefelé, és a **1200.76** értéket adja vissza. 

## <a name="example-2"></a>2. példa

A `ROUNDDOWN (1700.767, -3)` az 1000 legközelebbi többszörösére kerekít lefelé, és az **1000** értéket jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)
