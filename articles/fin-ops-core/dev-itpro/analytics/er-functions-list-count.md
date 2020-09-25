---
title: COUNT ER-függvény
description: A témakör tájékoztatást nyújt a COUNT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: c48483a6677aaeb36eac57a57cec71bf54c7991d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745345"
---
# <a name="count-er-function"></a>COUNT ER-függvény

[!include [banner](../includes/banner.md)]

A `COUNT` függvény egy *Egész* értéket ad eredményül, amely a megadott listában szereplő rekordok számát jelképezi, ha a lista nem üres. Ha a lista üres, a függvény **0** (nulla) értéket ad vissza.

## <a name="syntax"></a>Szintaxis

```vb
COUNT (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="example"></a>Példa

A `COUNT (SPLIT("abcd" , 3))` a **2** értéket adja vissza, mert a példában használt `SPLIT` függvény létrehoz egy listát, amely két rekordból áll.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
