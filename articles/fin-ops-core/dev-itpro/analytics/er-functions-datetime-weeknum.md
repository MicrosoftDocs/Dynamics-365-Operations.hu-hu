---
title: WEEKNUM ER függvény
description: Ez a cikk a WEEKNUM Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 2c6eef0d6e1f90a3f8d382591edad3d568da84ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858770"
---
# <a name="weeknum-er-function"></a>WEEKNUM ER függvény

[!include [banner](../includes/banner.md)]

A `WEEKNUM` függvény egy egész értéket ad *[...](er-formula-supported-data-types-primitive.md#integer)* vissza, amely egy adott dátumértéket tartalmazó év hetének *[megfelelő egész értéket ad](er-formula-supported-data-types-primitive.md#date)* vissza. A számítás a naptári hetet és a hét első napját meghatározó kultúrafüggő szabályokon alapul.

## <a name="syntax"></a>Szintaxis

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argumentumok</a>

`date`: *Dátum*

Az év hetének kiszámításához használt dátumnak megfelelő dátumérték.

`culture`: Karakterlánc *[...](er-formula-supported-data-types-primitive.md#string)*

A számításhoz használt kulturális környezet. A .NET szabványokkal összhangban támogatott kulturális kódok [használhatók](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0).

## <a name="return-values"></a>Visszatérési értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Az év hetének [számítása az ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) szabvány alapján történik, ha a szabványt olyan ország vagy régió elfogadta, amely számára futásidőben meg van biztosítanak a területi adatok. Ellenkező esetben a számítás az ország-/régióspecifikus nemzeti szabványokon alapul.

Ha futásidőben [nem](#arguments)`WEEKNUM` támogatott kulturális kódot ad meg a függvény argumentumaként, akkor a program kivételt ad. Ha az üres karakterlánc kulturális kódot tartalmaz, akkor a program az angol országsemleges naptárat használja a heti szám kiszámításához.

## <a name="examples"></a>Példák

A `WEEKNUM (DATEVALUE ("01-01-2020", "de"))` a **1** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2021", "de"))` a **53** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2022", "de"))` a **52** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` a **21** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Dátum- és időfüggvények](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
