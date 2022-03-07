---
title: CONCATENATE ER-függvény
description: A témakör tájékoztatást nyújt a CONCATENATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 1507e1b8a31ed45e7c540e4e2ff31b79e8de3b866ffbace9de17d7b3e169e877
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762500"
---
# <a name="concatenate-er-function"></a>CONCATENATE ER-függvény

[!include [banner](../includes/banner.md)]

A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.

## <a name="syntax"></a>Szintaxis

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumentumok

`text 1`: *Karakterlánc*

Hivatkozás a *Karakterlánc* adattípusú adatforrásra. Az argumentum megadása kötelező.

`text N`: *Karakterlánc*

Hivatkozás a *Karakterlánc* adattípusú adatforrásra. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.

## <a name="usage-notes"></a>Használati megjegyzések

Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]