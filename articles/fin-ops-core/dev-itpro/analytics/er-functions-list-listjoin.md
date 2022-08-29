---
title: LISTJOIN ER-függvény
description: Ez a cikk a LISTJOIN Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ec8a5985277de8036ec8ad51b947a8bab098a1c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291204"
---
# <a name="listjoin-er-function"></a>LISTJOIN ER-függvény

[!include [banner](../includes/banner.md)]

A `LISTJOIN` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistát jelenít meg.

## <a name="syntax"></a>Szintaxis

```vb
LISTJOIN (list 1 [, list 2, …, list N])
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

![Elektronikus jelentéskészítés – modell-leképezés tervező oldal.](./media/er-functions-list-listjoin-image1.gif)

Ebben az esetben a `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` kifejezés egy új, két rekordot tartalmazó listát ad eredményül.

![ER Modell-leképezés tervező lapja két rekorddal.](./media/er-functions-list-listjoin-image2.gif)

A lista szerkezete a `Real` típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.

![Elektronikus jelentéskészítés tervező oldalának mennyiség mezője.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)

[Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
