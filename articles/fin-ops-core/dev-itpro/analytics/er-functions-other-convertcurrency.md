---
title: CONVERTCURRENCY ER-függvény
description: A témakör tájékoztatást nyújt a CONVERTCURRENCY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: dc71ccedcdfc8a3dc9d7e087d29467bd3bbe72c3c5588872dbeaf3aa1dd35d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738600"
---
# <a name="convertcurrency-er-function"></a>CONVERTCURRENCY ER-függvény

[!include [banner](../includes/banner.md)]

A `CONVERTCURRENCY` függvény egy *Real* értéket ad vissza, ami a megadott forráspénzösszeg konvertálását képviseli az eredeti pénznemről a megadott cél pénznemre a megadott vállalat beállításainak használata segítségével a megadott időpontban.

## <a name="syntax"></a>Szintaxis

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]