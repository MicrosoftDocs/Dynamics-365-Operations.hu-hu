---
title: NULLCONTAINER ER-függvény
description: A témakör tájékoztatást nyújt a NULLCONTAINER Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: af6651ef3c62bd8d1285fa8179ac923d3c333ce7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746507"
---
# <a name="nullcontainer-er-function"></a>NULLCONTAINER ER-függvény

[!include [banner](../includes/banner.md)]

A `NULLCONTAINER` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.

## <a name="syntax"></a>Szintaxis

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista* vagy *Tároló (rekord)*

A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="usage-notes"></a>Használati megjegyzések

> [!NOTE] 
> Ez a funkció már elavult. Használja helyette az `EMPTYRECORD` függvényt. További tudnivalók: [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Példa

A `NULLCONTAINER (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának. További tudnivalók: [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>További erőforrások

[Rekord függvények](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]