---
title: ROUNDUP ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDUP Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 83262a11f92a924e5e49461cf414fb07ab278541
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744503"
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
