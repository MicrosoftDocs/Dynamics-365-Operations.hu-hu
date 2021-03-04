---
title: CHAR ER-függvény
description: A témakör tájékoztatást nyújt a CHAR Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: a9f0f70c250592bf74b1a1df823e66803e853a64
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682991"
---
# <a name="char-er-function"></a>CHAR ER-függvény

[!include [banner](../includes/banner.md)]

A `CHAR` függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.

## <a name="syntax"></a>Szintaxis

```vb
CHAR (number)
```

## <a name="arguments"></a>Argumentumok

`number`: *Egész*

A várt egyetlen karakternek megfelelő szám.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A funkció által visszaadott karakterlánc a szülő **FÁJL** formátumelemben kiválasztott kódolástól függ. A támogatott kódolások listájához lásd: [Kódolási osztály](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Példa

A `CHAR (255)` a **"ÿ"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]