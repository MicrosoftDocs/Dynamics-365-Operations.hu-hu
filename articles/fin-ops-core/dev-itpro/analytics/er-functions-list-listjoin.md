---
title: LISTJOIN ER-függvény
description: A témakör tájékoztatást nyújt a LISTJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9346afc88adb89c08098f39a5fd1c2cb82f664af2244b8cafbbe8a4d2f516c6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755802"
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
