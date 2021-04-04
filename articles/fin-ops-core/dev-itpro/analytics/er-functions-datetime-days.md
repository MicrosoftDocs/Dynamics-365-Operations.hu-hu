---
title: DAYS ER-függvény
description: A témakör tájékoztatást nyújt a DAYS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 0252a68aebaa9af95de561b88ceb0666b3460d79
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563486"
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