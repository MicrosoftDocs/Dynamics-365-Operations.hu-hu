---
title: ENDSWITH ER függvény
description: Ez a cikk az ENDSWITH elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 2608593238e5b2f738b452fb042837238f17e44e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271613"
---
# <a name="endswith-er-function"></a>ENDSWITH ER függvény

[!include [banner](../includes/banner.md)]

Az `ENDSWITH` függvény határozza meg, hogy a megadott bemenet a megadott szöveggel végződik-e. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre végződik. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A *Sztring* típusú adatforrás elemének vagy egy sztring konstans érvényes útvonala, amelynek értéke a második argumentummal zárulhat.

`start text`: *Karakterlánc*

A *Sztring* típusú adatforrás vagy egy sztring konstans érvényes útvonala, amely az első argumentum végén lehet.

## <a name="return-values"></a>Visszatérési értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ezzel a funkcióval csak akkor lehet megadni a [FILTER](er-functions-list-filter.md) függvény feltételkifejezését, ha a megfelelő hozzárendelés a [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) be van állítva a [Microsoft Dataverse](/power-platform/admin/data-integrator) szolgáltatáshoz való hozzáféréshez. Ellenkező esetben a rendszer kivételt ad a tervezéskor. A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a [WHERE](er-functions-list-where.md) függvény helyett a `FILTER` függvényt használja.

## <a name="example-1"></a>1. példa

Az `ENDSWITH ("abc", "d")` **HAMIS** eredményt ad, az `ENDSWITH ("abc", "C")` kifejezés pedig **IGAZ** eredményt ad.

## <a name="example-2"></a>2. példa

Az `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` kifejezés értéke **IGAZ**, ha a **modell** adatforrás **Cím** mezőjének értéke az **USA** sztringgel végződik. Ellenkező esetben **HAMIS** választ jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)
