---
title: SUMIF ER-függvény
description: A témakör tájékoztatást nyújt a SUMIF Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 52f9cdb78efa6fe0dbebd2ffd78cd6e9185d6b2e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685351"
---
# <a name="sumif-er-function"></a>SUMIF ER-függvény

[!include [banner](../includes/banner.md)]

A `SUMIF` függvény egy *Valós* értéket ad eredményül, amely a formátumelemek kötései által visszaadott értékek összegét mutatja, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt. A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.

## <a name="syntax"></a>Szintaxis

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Argumentumok

`key name for summing`: *Karakterlánc*

Az az érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés ad vissza, amelynek az összegzéshez a kötés értékét kell használni.

Az **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.

A `condition range` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

A `condition value` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.

## <a name="example"></a>Példa

Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).

A funkció használatával kapcsolatos további példákat és tudnivalókat lásd: [A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-sequence-element.md#Example) és [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md#Example).

## <a name="additional-resources"></a>További erőforrások

[Adatgyűjtési függvények](er-functions-category-data-collection.md)
