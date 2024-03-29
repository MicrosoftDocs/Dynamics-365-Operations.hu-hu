---
title: TRANSLATE ER-függvény
description: Ez a cikk az TRANSLATE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 7a15a28f6efa5333b54aa34938d22a9d6e404cec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278441"
---
# <a name="translate-er-function"></a>TRANSLATE ER-függvény

[!include [banner](../includes/banner.md)]

A `TRANSLATE` függvény olyan *Karakterlánc* értéket ad vissza, amely a megadott szöveg karakterrel történő helyettesítésének eredményét tartalmazza egy másik megadott halmaz karaktereivel.

## <a name="syntax"></a>Szintaxis

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

A *Karakterlánc* típus adatforrásának érvényes elérési útja.

`pattern`: *Karakterlánc*

A lecserélendő szöveg.

`replacement`: *Karakterlánc*

A csereként használandó szöveg.

## <a name="return-values"></a>Visszatérési értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A `TRANSLATE` függvény egyszerre csak egy karaktert cserél. A függvény cseréli a `text` argumentum első karakterét az `pattern` argumentum első karakterével, majd a második karakterrel, és a ugyanezt a folyamatot követi a befejezésig. Amikor egy karakter a `text` és a `pattern` az argumentumok között megegyezik, a program az `replacement` argumentumban szereplő karakternek karakterével helyettesíti, amely ugyanabban a pozícióban van, mint a `pattern` argumentum karaktere. Ha egy karakter többször jelenik meg az `pattern` argumentumban, akkor a `replacement` argumentum leképezése megfelel a karakter első előfordulásakor használtnak.

## <a name="example-1"></a>1. példa

A `TRANSLATE ("abcdef", "cd", "GH")` cseréli a **„c”** karakterét a meghatározott **„abcdef”** szövegnek a **„G”** karkaterére a `replacement` szövegnek a következők miatt:
-   A **„c ”** karakter az első pozícióban található a `pattern` szövegben.
-   A `replacement` szöveg első pozíciójában a **„G”** karakter szerepel.

## <a name="example-2"></a>2. példa

A `TRANSLATE ("abcdef", "ccd", "GH")` az **„abGdef”** értéket adja vissza.

## <a name="example-3"></a>3. példa

A `TRANSLATE ("abccba", "abc", "123")` a **"123321"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
