---
title: DAYS ER-függvény
description: A témakör tájékoztatást nyújt a DAYS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 310359a29a506d69d1f34aaa710a82b0f2ea528e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746891"
---
# <a name="days-er-function"></a>DAYS ER-függvény

[!include [banner](../includes/banner.md)]

A `DAYS` függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja.

## <a name="syntax"></a>Szintaxis

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argumentumok

`date 1`: *Dátum*

A napok számának kiszámításához a kezdési dátumot jelképező dátumérték.

`date 2`: *Dátum*

A napok számának kiszámításához a befejező dátumot jelképező dátumérték.

## <a name="return-values"></a>Visszaadott értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

A `DAYS` függvény pozitív értéket ad vissza, ha az első dátum későbbi, mint a második dátum, **0** (nulla) értéket ad vissza, ha az első dátum megegyezik a második dátummal, vagy pedig negatív értéket ad vissza, ha az első dátum korábbi a második dátumnál.

## <a name="example"></a>Példa

A `DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` a **-1** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]