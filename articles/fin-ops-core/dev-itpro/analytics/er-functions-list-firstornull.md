---
title: FIRSTORNULL ER függvény
description: A témakör tájékoztatást nyújt a FIRSTORNULL Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 18c8f79d7d6306d9973c5a3f129b9cde38d05d58502a2c83ac89a2bd10aaaeab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749709"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL ER függvény

[!include [banner](../includes/banner.md)]

A `FIRSTORNULL` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres. Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza.

## <a name="syntax"></a>Szintaxis

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example"></a>Példa

A `FIRSTORNULL(SPLIT("",1)).Value` kifejezés üres karakterláncot ad eredményül (**""**).

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]