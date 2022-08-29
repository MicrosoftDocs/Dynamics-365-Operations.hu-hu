---
title: SPLITLIST ER-függvény
description: Ez a cikk a SPLITLIST Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 03/15/2021
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
ms.openlocfilehash: 38ac7e6c6bdf53705d1374c173422f7347253a5f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292526"
---
# <a name="splitlist-er-function"></a>SPLITLIST ER-függvény

[!include [banner](../includes/banner.md)]

A `SPLITLIST` függvény a megadott listát allistákká (vagy kötegekké) osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz. Ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.

## <a name="syntax-1"></a>Szintaxis 1

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`number`: *Egész*

A rekordok maximális száma kötegenként.

`on-demand reading flag`: *Logikai*

Egy *Logikai* érték, amely meghatározza, hogy az allisták elemeit igény szerint létre kell-e hozni.

## <a name="return-values"></a>Visszatérési értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A visszaadott kötegek listája a következő elemeket tartalmazza:

 - **Érték:** *Lista*

    Az aktuális köteghez tartozó rekordlista.

- **BatchNumber:** *Egész*

    Az aktuális köteg száma a visszaadott listában.

Ha az igény szerinti olvasási jelző **Igaz** értékre van állítva, kérésre allisták jönnek létre, amelyek lehetővé teszik a memóriafelhasználás csökkentését, de teljesítménycsökkenést okozhatnak, ha az elemeket nem egymás után használják.

## <a name="example"></a>Példa

Az alábbi példában egy **Sorok** adatforrás jön létre rekordlistaként, amely három rekorddal rendelkezik. Ez a kötegekre tételekre oszlik, amelyek mindegyike legfeljebb két rekordot tartalmaz.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Az alábbi ábrán a tervezett formátumelrendezés látható. Ebben a formátumelrendezésben a **Sorok** adatforráshoz kötések jönnek létre a kimenet XML-formátumú előállításához. Ez a kimenet minden egyes kötethez és a hozzá tartozó rekordokhoz egyedi csomópontokat tartalmaz.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
