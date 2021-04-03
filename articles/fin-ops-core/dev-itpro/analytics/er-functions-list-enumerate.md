---
title: ENUMERATE ER-függvény
description: A témakör tájékoztatást nyújt az ENUMERATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 0827fe33a548970c7673ac2ab830bb22d367c8cc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567868"
---
# <a name="enumerate-er-function"></a>ENUMERATE ER-függvény

[!include [banner](../includes/banner.md)]

Az `ENUMERATE` függvény egy új *Rekordlista* értéket ad vissza, amely a megadott lista felsorolt rekordjaiból áll.

## <a name="syntax"></a>Szintaxis

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A felsorolt rekordok listája a következő további elemeket jeleníti meg:

- A mezők rekordja (**Érték** összetevő)
- Az aktuális rekord index (**Szám** összetevő)

## <a name="example"></a>Példa

A következő ábrán az **Sorszámozott** adatforrás a szállítói rekordok sorszámozott listájaként jött létre a **Szállítók** adatforrásból, amely a VendTable táblára hivatkozik.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

A következő ábrán az Elektronikus jelentéskészítési (ER) formátum látható. Ebben a formátumelrendezésben adatkötések jönnek létre a kimenet XML-formátumú előállításához. A kimenet az egyes szállítókat sorszámozott csomópontként jeleníti meg.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]