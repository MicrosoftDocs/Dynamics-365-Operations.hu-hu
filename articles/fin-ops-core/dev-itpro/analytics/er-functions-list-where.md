---
title: WHERE ER-függvény
description: Ez a cikk az Elektronikus jelentéskészítés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 90b9309b30986837855fb96389b234e504dadd4d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847517"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]