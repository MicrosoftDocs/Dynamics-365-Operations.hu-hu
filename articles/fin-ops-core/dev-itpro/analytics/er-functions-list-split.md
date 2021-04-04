---
title: SPLIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLIT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 806a0995f0c138f4e80396bb993bc6f41bc7c827
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567342"
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

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]