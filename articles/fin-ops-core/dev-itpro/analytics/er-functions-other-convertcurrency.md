---
title: CONVERTCURRENCY ER-függvény
description: A témakör tájékoztatást nyújt a CONVERTCURRENCY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf972c6c2cc798811a9fb3bd3a355ac6ffca5a60
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915947"
---
# <a name="CONVERTCURRENCY">CONVERTCURRENCY ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `CONVERTCURRENCY` függvény egy *Real* értéket ad vissza, ami a megadott forráspénzösszeg konvertálását képviseli az eredeti pénznemről a megadott cél pénznemre a megadott vállalat beállításainak használata segítségével a megadott időpontban.

## <a name="syntax"></a>Szintaxis

```
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argumentumok

`amount`: *Egész* vagy *Valós*

A konvertálni kívánt pénzösszeget jelölő numerikus érték.

`source currency`: *Karakterlánc*

A forráspénznem kódja.

`target currency`: *Karakterlánc*

A célpénznem kódja.

`date`: *Dátum*

Egy *Dátum* érték, amely a konverzió árfolyamát meghatározó dátumot jelöli.

`company`: *Karakterlánc*

Egy *Karakterlánc* érték, amely egy olyan vállalat kódját jelöli, amely a konvertáláshoz használt beállításokat szolgáltatja.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="example"></a>Példa

A `CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` egy euró egyenértékét jeleníti meg USA-dollárban az aktuális munkameneti napon a **DEMF** vállalat beállításai alapján.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)
