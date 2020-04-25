---
title: LISTJOIN ER-függvény
description: A témakör tájékoztatást nyújt a LISTJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249035"
---
# <a name=""></a><a name="LISTJOIN">LISTJOIN ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `LISTJOIN` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistát jelenít meg.

## <a name="syntax"></a>Szintaxis

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argumentumok

`list 1`: *Rekordlista*

Hivatkozás a *Rekordlista* adattípusú adatforrásra. Az argumentum megadása kötelező.

`list N`: *Rekordlista*

Hivatkozás a *Rekordlista* adattípusú adatforrásra. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszatérési értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A létrehozott lista szerkezete csak azokat a mezőket tartalmazza, amelyek az argumentumban szereplő minden rekordlista struktúrájában láthatók.

## <a name="example"></a>Példa

Adja meg az **1. rekord** adatforrását a `Container` típushoz. Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:

- **Kód**: Ez a mező egy olyan kifejezést tartalmaz, amely a `String` típus értékét adja eredményül.
- **Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.

Majd adja meg a **2. rekord** adatforrását a `Container` típushoz. Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:

- **Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.
- **IsValid**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Boolean` típus értékét adja eredményül.

Ebben az esetben a `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` kifejezés egy új, két rekordot tartalmazó listát ad eredményül. A lista szerkezete a `Real` típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
