---
title: ROUNDAMOUNT ER-függvény
description: Ez a cikk a ROUNDAMOUNT Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 0e4de43f865ca21822ab2c0c345026d2e9113ca2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286029"
---
# <a name="roundamount-er-function"></a>ROUNDAMOUNT ER-függvény

[!include [banner](../includes/banner.md)]

A `ROUNDAMOUNT` függvény egy *Valós* értéket ad vissza a megadott szám egy másik szám legközelebbi többszörösére való kerekítésének eredményeként a megadott kerekítési szabályok szerint.

## <a name="syntax"></a>Szintaxis

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argumentumok

`number`: *Int* vagy *Valós*

Kerekítendő numerikus érték.

`decimals`: *Int* vagy *Valós*

A szám, amelynek többszörösére a `number` paraméter értékét kerekíteni kell.

`round rule`: *Felsorolási érték*

A **RoundOffType** felsorolás felsorolási értéke, amely meghatározza a kerekítési szabályt. Ez a felsorolás a következő értékeket nyújtja:

- Normál (Ordinary)
- Lefelé (RoundDown)
- Felfelé kerekítés (RoundUp)

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték a `decimals` paraméterben megadott érték többszöröse, és a legközelebb áll a `number` paraméterben megadott értékhez.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a `number` paraméter nulla, ez a funkció mindig nullát ad eredményül.

Ha a `decimals` paraméter értéke nulla, ez a függvény az alapértelmezett kerekítési értékre kerekít. Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, az alapértelmezett kerekítési érték **0,01**. Ellenkező esetben az alapértelmezett kerekítés értéke **1,0**.

Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, ez a függvény a legközelebbi kerekítési összegre kerekít.

Ha a `round rule` paraméter értéke **RoundOffType.RoundDown**, ez a függvény nulla irányában a legközelebbi kerekítési összegre kerekít.

Ha a `round rule` paraméter értéke **RoundOffType.RoundUp**, ez a függvény nullával ellenkező irányában a legközelebbi kerekítési összegre kerekít.

Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, ez a függvény úgy viselkedik, mint az [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel-függvény és a [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) X++-függvény.

## <a name="remarks"></a>Megjegyzések

Ha egy numerikus értéket adott számú tizedesjegyre szeretne kerekíteni, használja a [ROUND](er-functions-mathematical-round.md) függvényt.

## <a name="example"></a>Példa

Ha a **model.RoundOff** paraméter **RoundOffType.Ordinary** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7,35 értéket ad vissza. 

Ha a **model.RoundOff** paraméter **RoundOffType.RoundDown** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7,35 értéket ad vissza. 

Ha a **model.RoundOff** paraméter **RoundOffType.RoundUp** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 8,4 értéket ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)

[Matematikai funkciók](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
