---
title: WHERE ER-függvény
description: A témakör tájékoztatást nyújt a WHERE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cc47c5001cf456b1fc600b326f826ea3b8b43ee
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687050"
---
# <a name="where-er-function"></a>WHERE ER-függvény

[!include [banner](../includes/banner.md)]

A `WHERE` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott feltételek szerint szűrésre került.

## <a name="syntax"></a>Szintaxis

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`condition`: *Logikai*

Érvényes feltételes kifejezés, amely a megadott lista rekordjainak szűrésére szolgál.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

Ez a függvény eltér a [FILTER](er-functions-list-filter.md) függvénytől, mivel a megadott feltétel a memóriában található összes *Rekordlista* típusú Elektronikus jelentéskészítési (ER) adatforrására alkalmazásra kerül.

Ha a függvényhez konfigurált argumentumok (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben egy figyelmeztető üzenet jelenik meg. Ez az üzenet arról tájékoztatja a felhasználót, hogy a teljesítmény javulhat, ha a [FILTER](er-functions-list-filter.md) függvényt használja a `WHERE` helyett.

## <a name="example-1"></a>1. példa

Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `WHERE (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.

## <a name="example-2"></a>2. példa

Ha megadja a *Számított mező* típusú **DS** adatforrását, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `WHERE( DS, DS.Value = "B")` kifejezés egyetlen rekordból álló listát ad vissza, ami tartalmazza a **„B”** szöveget az **Érték** mezőben.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
