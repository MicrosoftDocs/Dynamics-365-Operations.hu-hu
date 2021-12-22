---
title: WEEKNUM ER függvény
description: Ez a témakör a WEEKNUM Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/03/2021
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
ms.openlocfilehash: fe36d4142b6e4922e2cbca09bb0ca9f68f6680a0
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891366"
---
# <a name="weeknum-er-function"></a>WEEKNUM ER függvény

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A függvény egy egész értéket ad vissza, amely egy adott dátumértéket tartalmazó év `WEEKNUM`*[...](er-formula-supported-data-types-primitive.md#integer)* hetének *[megfelelő egész értéket](er-formula-supported-data-types-primitive.md#date)* ad vissza. A számítás a naptári hetet és a hét első napját meghatározó kultúrafüggő szabályokon alapul.

## <a name="syntax"></a>Szintaxis

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argumentumok</a>

`date`: *Dátum*

Az év hetének kiszámításához használt dátumnak megfelelő dátumérték.

`culture`: *[Karakterlánc](er-formula-supported-data-types-primitive.md#string)*

A számításhoz használt kulturális környezet. A .NET szabványokkal összhangban támogatott kulturális kódok [használhatók](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0).

## <a name="return-values"></a>Visszatérési értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Az év hetének számítása az ISO 8601 szabvány alapján történik, ha a szabványt olyan ország vagy régió elfogadta, amely számára futásidőben meg van biztosítanak [a](https://www.iso.org/iso-8601-date-and-time-format.html) területi adatok. Ellenkező esetben a számítás az ország-/régióspecifikus nemzeti szabványokon alapul.

Ha futásidőben nem támogatott [kulturális](#arguments) kódot ad meg a függvény argumentumaként, akkor a program `WEEKNUM` kivételt ad. Ha az üres karakterlánc kulturális kódot tartalmaz, akkor a program az angol országsemleges naptárat használja a heti szám kiszámításához.

## <a name="examples"></a>Példák

A `WEEKNUM (DATEVALUE ("01-01-2020", "de"))` a **1** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2021", "de"))` a **53** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2022", "de"))` a **52** értéket adja vissza.

A `WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` a **21** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Dátum- és időfüggvények](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
