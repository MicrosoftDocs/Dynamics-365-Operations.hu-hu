---
title: SPLITLIST ER-függvény
description: A témakör tájékoztatást nyújt a SPLITLIST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: d0f527dcf313a6a5e3b6601cac9a0f6495f66833
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680339"
---
# <a name="splitlist-er-function"></a>SPLITLIST ER-függvény

[!include [banner](../includes/banner.md)]

A `SPLITLIST` függvény a megadott listát allistákká (vagy kötegekké) osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz. Ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.

## <a name="syntax"></a>Szintaxis

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`number`: *Egész*

A rekordok maximális száma kötegenként.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A visszaadott kötegek listája a következő elemeket tartalmazza:

 - **Érték:** *Lista*

    Az aktuális köteghez tartozó rekordlista.

- **BatchNumber:** *Egész*

    Az aktuális köteg száma a visszaadott listában.

## <a name="example"></a>Példa

Az alábbi példában egy **Sorok** adatforrás jön létre rekordlistaként, amely három rekorddal rendelkezik. Ez a kötegekre tételekre oszlik, amelyek mindegyike legfeljebb két rekordot tartalmaz.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Az alábbi ábrán a tervezett formátumelrendezés látható. Ebben a formátumelrendezésben a **Sorok** adatforráshoz kötések jönnek létre a kimenet XML-formátumú előállításához. Ez a kimenet minden egyes kötethez és a hozzá tartozó rekordokhoz egyedi csomópontokat tartalmaz.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
