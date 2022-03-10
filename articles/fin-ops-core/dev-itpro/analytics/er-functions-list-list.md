---
title: LIST ER-függvény
description: A témakör tájékoztatást nyújt a LIST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ac8d3971a5502ce567069e0c97247d75a25ae3d38e2cd91e875d4c0d2681d01d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747321"
---
# <a name="list-er-function"></a>LIST ER-függvény

[!include [banner](../includes/banner.md)]

A `LIST` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistából áll.

## <a name="syntax"></a>Szintaxis

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argumentumok

`record 1`: *Tároló (rekord)*

Hivatkozás a *Rekord* adattípusú adatforrásra. Az argumentum megadása kötelező.

`record N`: *Tároló (rekord)*

Hivatkozás a *Rekord* adattípusú adatforrásra. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A létrehozott lista szerkezete csak azokat a mezőket tartalmazza, amelyek az argumentumban szereplő minden rekord struktúrájában láthatók.

## <a name="example"></a>Példa

Adja meg a *Tároló* típus **1. rekord** adatforrását. Ez az adatforrás a *Kiszámított mező* típus alábbi beágyazott mezőit tartalmazza:

- **Kód:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Karakterlánc* típus értékét adja eredményül.
- **Mennyiség:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Valós* típus értékét adja eredményül.

Ezután adja meg a *Tároló* típus **2. rekord** adatforrását. Ez az adatforrás a *Kiszámított mező* típus alábbi beágyazott mezőit tartalmazza:

- **Mennyiség:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Valós* típus értékét adja eredményül.
- **IsValid:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Logikai* típus értékét adja eredményül.

Ebben az esetben a `LIST('Record 1', 'Record 2')` kifejezés egy új, két rekordot tartalmazó listát ad eredményül. A lista szerkezete a *valós* típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]