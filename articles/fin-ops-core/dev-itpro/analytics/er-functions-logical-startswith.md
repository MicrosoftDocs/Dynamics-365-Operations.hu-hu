---
title: STARTSWITH ER függvény
description: Ez a cikk a STARTSWITH Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: a9c22154484f9e98dbe101b5de0f539b2feb9865
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883727"
---
# <a name="startswith-er-function"></a>STARTSWITH ER függvény

[!include [banner](../includes/banner.md)]

A `STARTSWITH` függvény határozza meg, hogy a megadott bemenet a megadott szöveggel kezdődik-e. A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre kezdődik. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A *Sztring* típusú adatforrás elemének vagy egy sztring konstans érvényes útvonala, amelynek értéke a második argumentummal kezdődhet.

`start text`: *Karakterlánc*

A *Sztring* típusú adatforrás vagy egy sztring konstans érvényes útvonala, amely az első argumentum elején lehet.

## <a name="return-values"></a>Visszatérési értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ezzel a funkcióval csak akkor lehet megadni a [FILTER](er-functions-list-filter.md) függvény feltételkifejezését, ha a megfelelő hozzárendelés a [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) be van állítva a [Microsoft Dataverse](/power-platform/admin/data-integrator) szolgáltatáshoz való hozzáféréshez. Ellenkező esetben a rendszer kivételt ad a tervezéskor. A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a [WHERE](er-functions-list-where.md) függvény helyett a `FILTER` függvényt használja.

## <a name="example-1"></a>1. példa

A `STARTSWITH ("abc", "d")` **HAMIS** eredményt ad, az `STARTSWITH ("abc", "A")` kifejezés pedig **IGAZ** eredményt ad.

## <a name="example-2"></a>2. példa

A `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` kifejezés értéke **IGAZ**, ha a **modell** adatforrás **Cím** mezőjének értéke az **123 Coffee Street** sztringgel kezdődik. Ellenkező esetben **HAMIS** választ jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)
