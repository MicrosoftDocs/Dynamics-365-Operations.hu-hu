---
title: CONTAINS ER függvény
description: A témakör tájékoztatást nyújt a CONTAINS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: a31d89f036a6e821bea2b6733c0c646145d2a47c
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048870"
---
# <a name="contains-er-function"></a>CONTAINS ER függvény

[!include [banner](../includes/banner.md)]

A `CONTAINS` funkció határozza meg, hogy a megadott bemenet tartalmazza-e a megadott szöveget. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet tartalmazza-e a megadott szöveget. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A *Sztring* típusú adatforrás elemének vagy egy sztring konstans érvényes útvonala, amelynek értéke tartalmazhatja a második argumentumot.

`search text`: *Karakterlánc*

A *Sztring* típusú adatforrás vagy egy sztring konstans érvényes útvonala, amely az első argumentumban lehet.

## <a name="return-values"></a>Visszatérési értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ezzel a funkcióval csak akkor lehet megadni a [FILTER](er-functions-list-filter.md) függvény feltételkifejezését, ha a megfelelő hozzárendelés a [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) be van állítva a [Microsoft Dataverse](/power-platform/admin/data-integrator) szolgáltatáshoz való hozzáféréshez. Ellenkező esetben a rendszer kivételt ad a tervezéskor. A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a [WHERE](er-functions-list-where.md) függvény helyett a `FILTER` függvényt használja.

## <a name="example-1"></a>1. példa

A `CONTAINS ("abc", "d")` **HAMIS** eredményt ad, az `CONTAINS ("abc", "C")` kifejezés pedig **IGAZ** eredményt ad.

## <a name="example-2"></a>2. példa

A `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` kifejezés értéke **IGAZ**, ha a **modell** adatforrás **Cím** mezőjének értéke tartalmazza a **DEU** sztringet. Ellenkező esetben **HAMIS** választ jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)
