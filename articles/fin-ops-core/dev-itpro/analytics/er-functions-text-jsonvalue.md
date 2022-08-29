---
title: JSONVALUE ER-függvény
description: Ez a cikk a JSONVALUE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 10/25/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267963"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `JSONVALUE` függvény elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítóval rendelkező skaláris érték kibontásához. Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket.

## <a name="syntax"></a>Szintaxis

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A JSON adatokat tartalmazó, *Karakterlánc* típusú adatforrás érvényes elérési útja.

`path`: *Karakterlánc*

A JSON adatok skaláris értékének azonosítója. Perjellel (/) válassza el a kapcsolódó JSON-csomópontok nevét. Zárójellel (\[\]) megadhatja egy adott érték indexét egy JSON-tömbben. Ne feledje, hogy ehhez az indexhez nullás számozást használ.

## <a name="return-values"></a>Visszatérési értékek

*Sztring*

Az eredményül kapott szövegérték.

## <a name="example-1"></a>1. példa

A **JsonField** adatforrás a következő adatokat tartalmazza JSON formátumban: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. Ebben az esetben a `JSONVALUE (JsonField, "BuildNumber")` kifejezés a következő *Karakterlánc* adattípusú értéket adja eredményül: **"7.3.1234.1"**.

## <a name="example-2"></a>2. példa

A **JsonField** adatforrása ami *Számított mező* típusú a következő kifejezést tartalmazza: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

Ez a kifejezés olyan [*Sztring*](er-formula-supported-data-types-primitive.md#string) értéket ad vissza, amely a következő adatokat képviseli JSON-formátumban.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

Ebben az esetben a `JSONVALUE(json, "workers/[1]/emails/[0]")` kifejezés a következő *Sztring* adattípusú értéket adja eredményül: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
