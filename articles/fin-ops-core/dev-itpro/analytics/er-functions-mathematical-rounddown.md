---
title: ROUNDDOWN ER-függvény
description: Ez a cikk a ROUNDDOWN Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: c651715a4a9c01f5c126ce16cd6238d86db5b144
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869344"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]