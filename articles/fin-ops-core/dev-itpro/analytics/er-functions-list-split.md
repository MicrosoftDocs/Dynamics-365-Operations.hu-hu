---
title: SPLIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLIT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 04/01/2021
ms.topic: article
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853443"
---
# <a name="split-er-function"></a>SPLIT ER-függvény

[!include [banner](../includes/banner.md)]

A `SPLIT` függvény az adott bemeneti karakterláncot részkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza.

## <a name="syntax-1"></a>Szintaxis 1

```vb
SPLIT (input, length)
```

Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, amelyek mindegyike megadott időtartammal rendelkezik.

## <a name="syntax-2"></a>Szintaxis 2

```vb
SPLIT (input, delimiter)
```

Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, megadott elválasztó alapján.

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A felosztandó szöveg.

`length`: *Egész*

Egyetlen részkarakterlánc maximális hossza.

`delimiter`: *Karakterlánc*

A részkarakterláncok elválasztására használt határolójel.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A visszaadott lista rekordstruktúrája a *Karakterlánc* típus **Érték** mezőjéből áll. A visszaadott lista minden rekordja az ebben a mezőben generált részkarakterláncokat tartalmazza.

Ha a `delimiter` argumentum üres, egy új listát ad vissza, amely egy rekordból áll, amelynek van egy *Karakterlánc* típusú **Érték** mezője. Ez a mező tartalmazza a beírt szöveget.

Ha az `input` argumentum üres, akkor egy új, üres listát ad vissza. Ha az `input` vagy `delimiter` argumentum nincs megadva (null), alkalmazáskivétel történik.

## <a name="example-1"></a>1. példa

A `SPLIT ("abcd", 3)` két rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek. Az első rekordban szereplő **Érték** mező az **„abc”** szöveget tartalmazza és a második rekordban szereplő **Érték** mező a **„d”** betűt tartalmazza.

## <a name="example-2"></a>2. példa

A `SPLIT ("XAb aBy", "aB")` három rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek. Az első rekordban szereplő **Érték** mező az **„X”** szöveget, a második rekordban szereplő **Érték** mező a **„&nbsp;”** szöveget, a harmadik rekordban szereplő **Érték** mező pedig az **„y”** szöveget tartalmazza. 

## <a name="example-3"></a>3. példa

Az [INDEX](er-functions-list-index.md) függvény segítségével lehet elérni a megadott bemeneti karakterlánc egyes elemeit. Ha megadja a **Számított mező** típusú **MyList** adatforrást, és konfigurálja hozzá a `SPLIT("abc", 1)` kifejezést, akkor a `INDEX(MyList,2).Value` kifejezés a **„b”** szöveges értéket adja vissza.

## <a name="example-4"></a>4. példa

Az [ENUMERATE](er-functions-list-enumerate.md) függvény segítségével szintén el lehet érni a megadott bemeneti karakterlánc egyes elemeit. Ha először a **Számított mező** típus **MyList** adatforrását adja meg, és annak konfigurálja a `SPLIT("abc", 1)` kifejezést, majd beírja a **Számított mező** típus **EnumeratedList** adatforrását, és konfigurálja a `ENUMERATE(MyList)` kifejezéshez, a `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` kifejezés a **„b”** szöveget adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
