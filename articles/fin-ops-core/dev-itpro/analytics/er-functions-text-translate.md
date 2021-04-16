---
title: TRANSLATE ER-függvény
description: A témakör tájékoztatást nyújt a TRANSLATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 7e4d6417757e27190ab7cabf2bf01243bb87b55c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746073"
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