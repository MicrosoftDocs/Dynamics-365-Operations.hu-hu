---
title: ISVALIDCHARACTERISO7064 ER-függvény
description: A témakör tájékoztatást nyújt a ISVALIDCHARACTERISO7064 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c3bceb15bbe1dc65abc88c1229459707a6166482
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680662"
---
# <a name="isvalidcharacteriso7064-er-function"></a>ISVALIDCHARACTERISO7064 ER-függvény

[!include [banner](../includes/banner.md)]

A `ISVALIDCHARACTERISO7064` függvény *logikai* **IGAZ** értéket ad vissza, ha a megadott karakterlánc érvényes nemzetközi bankszámlaszámnak (IBAN) felel meg. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy IBAN értéket képviselő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

Az `ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` **IGAZ** értéket ad vissza. 

Az `ISVALIDCHARACTERISO7064 ("AT61")` **HAMIS** értéket ad vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)
