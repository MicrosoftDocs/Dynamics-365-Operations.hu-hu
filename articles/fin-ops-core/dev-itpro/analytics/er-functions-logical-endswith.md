---
title: ENDSWITH ER függvény
description: A témakör tájékoztatást nyújt az ENDSWITH Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 02/11/2021
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
ms.openlocfilehash: d2fa1c0e61e964de9b7dff36fe6a8c2813802e1cc22341ce4ddd73a17751a9c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771984"
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
