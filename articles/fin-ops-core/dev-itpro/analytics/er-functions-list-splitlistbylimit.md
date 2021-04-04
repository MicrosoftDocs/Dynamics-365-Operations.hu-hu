---
title: SPLITLISTBYLIMIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLITLISTBYLIMIT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: 119ad3c363913ddaf3d6b890e36989d03e91b3c0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565104"
---
# <a name="splitlistbylimit-er-function"></a>SPLITLISTBYLIMIT ER-függvény

[!include [banner](../includes/banner.md)]

A `SPLITLISTBYLIMIT` függvény a megadott listát az allisták (kötegek) új listájára osztja fel. Az egyes kötegekben lévő rekordok számát dinamikusan számítja a rendszer. A függvény ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.

## <a name="syntax"></a>Szintaxis

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`limit value`*Egész* vagy *Valós*

Az eredeti listának a kötegekben való felosztása során használt korlát maximális értéke.

`limit source`: *Mező*

Az *Egész* vagy *Valós* típusú mezők érvényes elérési útja a megadott listában. Ennek a mezőnek az értéke azt a lépést határozza meg, amellyel a teljes összeg növelhető.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A visszaadott kötegek listája a következő elemeket tartalmazza:

- **Érték**: *Lista*

    Az aktuális köteghez tartozó rekordlista.

- **BatchNumber**: *Egész*

    Az aktuális köteg száma a visszaadott listában.

A rendszer nem használja a korlátot az eredeti lista egyetlen eleménél, amikor a korlát forrása meghaladja a meghatározott határértéket.

## <a name="example"></a>Példa

A következő ábrán egy Elektronikus jelentéskészítési (ER) formátum látható.

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

Az alábbi ábrákon láthatók az adatforrások, amelyek használatosak a formátumhoz.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

Az alábbi ábrán a formátum futtatásának eredménye látható. Ebben az esetben a kimenet egy egyszerű lista árucikkekről.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

A következő ábrákon ugyanezt a formázást módosítottuk, hogy az árucikkcsoportok listáját kötegekben mutassa be, amikor egy-egy kötegnek árucikkeket kell tartalmaznia, és a teljes súly nem haladhatja meg a 9-es határértéket.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

Az alábbi ábrán a módosított formátum futtatásának eredménye látható.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> A korlát nem vonatkozik az eredeti lista utolsó elemére, mivel a korlát forrásának (**súly**) értéke (**11**) meghaladja a meghatározott határértéket (**9**). Az allisták figyelmen kívül hagyásához a jelentéskészítés során használja a `WHERE` függvényt vagy a megfelelő formátumelem **Engedélyezett** kifejezését, ha szükséges.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]