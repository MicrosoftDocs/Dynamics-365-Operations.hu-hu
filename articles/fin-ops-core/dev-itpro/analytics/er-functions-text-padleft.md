---
title: PADLEFT ER-függvény
description: A témakör tájékoztatást nyújt a PADLEFT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 268941d8bc0bd4dc6de6d2597c05a11c1f530f15
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680146"
---
# <a name="padleft-er-function"></a>PADLEFT ER-függvény

[!include [banner](../includes/banner.md)]

A `PADLEFT` függvény egy megadott hosszúságú *Karakterlánc* értéket ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.

## <a name="syntax"></a>Szintaxis

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Az eredeti szöveget jelölő *Karakterlánc* érték.

`length`: *Egész*

A kitöltött karakterláncban a karakterek végső számát jelölő *Egész* szám.

`padding chars`: *Karakterlánc*

Kitöltésként használandó karakterek.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `PADLEFT ("1234", 10, "`&nbsp;`")` a következő szöveges karakterláncot adja vissza: **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]