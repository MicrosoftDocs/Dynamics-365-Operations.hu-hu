---
title: COUNTIF ER-függvény
description: Ez a cikk a COUNTIF elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 60a17d6a5e089cc6006a5fb3493654963de1b392
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906858"
---
# <a name="countif-er-function"></a>COUNTIF ER-függvény

[!include [banner](../includes/banner.md)]

A `COUNTIF` függvény egy *Egész* értéket ad eredményül, amely azoknak a formátumelemeknek a számát adja vissza, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt. A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.

## <a name="syntax"></a>Szintaxis

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a>Argumentumok

`condition range`: *Karakterlánc*

Olyan érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.

`condition value`: *Karakterlánc*

Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.

## <a name="return-values"></a>Visszaadott értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Az **Gyűjtött adatkulcs neve** és a **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** alatt található, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.

Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.

A `condition range` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

A `condition value` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

## <a name="example"></a>Példa

Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).

## <a name="additional-resources"></a>További erőforrások

[Adatgyűjtési függvények](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]