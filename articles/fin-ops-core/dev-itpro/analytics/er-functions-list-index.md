---
title: INDEX ER-függvény
description: Ez a cikk az INDEX elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 051a2818d862c3bc517e8c20a1742c2599c3bba6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854785"
---
# <a name="index-er-function"></a>INDEX ER-függvény

[!include [banner](../includes/banner.md)]

Az `INDEX` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott numerikus index használatával került kiválasztásra a megadott listában. Kivétel történik, ha az index kívül esik a listán megadott rekordok tartományán.

## <a name="syntax"></a>Szintaxis

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`index`: *Egész*

Numerikus index, amely a kívánt rekord pozícióját jelzi a megadott listában.

> [!NOTE]
> Mivel ehhez a funkcióhoz egyen alapuló számozást kell használni, a megadott lista első rekordjának visszaadásához adja meg az **1** értéket.

## <a name="return-values"></a>Visszatérési értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example-1"></a>1. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `DS.Value` kifejezés a **„B”** szöveges értéket adja vissza a rekordlista második rekordjaként. Az `INDEX (SPLIT ("A|B|C", "|"), 2).Value` kifejezés szintén a **„B”** szöveges értéket adja eredményül.

## <a name="example-2"></a>2. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor az `INDEX (SPLIT ("A|B|C", "|"), 4).Value` kifejezés kivételt dob futásidőben.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
