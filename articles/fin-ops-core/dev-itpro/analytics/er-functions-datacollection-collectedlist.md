---
title: COLLECTEDLIST ER-függvény
description: A témakör tájékoztatást nyújt a COLLECTEDLIST Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: d02f9ac4697a4d65417e522bffb5f40ebfdc237a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681232"
---
# <a name="collectedlist-er-function"></a>COLLECTEDLIST ER-függvény

[!include [banner](../includes/banner.md)]

A `COLLECTEDLIST` függvény olyan *Rekordlista* értéket ad eredményül, amely tartalmazza azon értékek listáját, amelyeket a formátumelemek **Gyűjtött adatkulcs értéke** tulajdonsága adott vissza, és amelyeket akkor gyűjtött, amikor a formátumelemeket kimenő dokumentumok létrehozására használták a formátumfuttatás során, és amelyek teljesítik a megadott követelményeket. Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.

## <a name="syntax"></a>Szintaxis

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argumentumok

`condition 1 range`: *Karakterlánc*

Olyan érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza. Az argumentum megadása kötelező.

`condition 1 value`: *Karakterlánc*

Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza. Az argumentum megadása kötelező.

`condition N range`: *Karakterlánc*

Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza. Ezek a további argumentumok nem kötelezők.

`condition N value`: *Karakterlánc*

Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

Az **Gyűjtött adatkulcs neve** és a **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** alatt található, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.

Ez a függvény üres listát ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.

A `condition range` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

A `condition value` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

## <a name="example"></a>Példa

Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).

## <a name="additional-resources"></a>További erőforrások

[Adatgyűjtési függvények](er-functions-category-data-collection.md)
