---
title: FORMATELEMENTNAME ER-függvény
description: A témakör tájékoztatást nyújt a FORMATELEMENTNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755228"
---
# <a name="formatelementname-er-function"></a>FORMATELEMENTNAME ER-függvény

[!include [banner](../includes/banner.md)]

A `FORMATELEMENTNAME` függvény egy *Karakterlánc* értéket ad eredményül, amely az aktuális Elektronikus jelentéskészítési (ER) formátum elemének nevét jelöli.

## <a name="syntax"></a>Szintaxis

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ez a funkció olyan ER-kifejezésekben hívható, amelyek egy ER-formátum összetevő **Gyűjtött adatkulcs neve** és **Gyűjtött adatkulcs értéke** tulajdonságához lettek konfigurálva, és amely ER-formátum a **Common\\File** összetevő **Szöveg** csoportjából származik, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.

## <a name="example"></a>Példa

Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).

## <a name="additional-resources"></a>További erőforrások

[Adatgyűjtési függvények](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]