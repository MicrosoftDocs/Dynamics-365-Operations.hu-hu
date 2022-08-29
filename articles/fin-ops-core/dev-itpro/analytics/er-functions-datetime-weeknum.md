---
title: WEEKNUM ER függvény
description: Ez a cikk a WEEKNUM Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 4658f88b7e353e651177fad0c8636c5403be1256
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268146"
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
