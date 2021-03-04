---
title: INDEX ER-függvény
description: A témakör tájékoztatást nyújt az INDEX Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: a49def8aaa5398fbc7e0f06cc26df8a745207c93
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687991"
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

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example-1"></a>1. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `DS.Value` kifejezés a **„B”** szöveges értéket adja vissza a rekordlista második rekordjaként. Az `INDEX (SPLIT ("A|B|C", "|"), 2).Value` kifejezés szintén a **„B”** szöveges értéket adja eredményül.

## <a name="example-2"></a>2. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor az `INDEX (SPLIT ("A|B|C", "|"), 4).Value` kifejezés kivételt dob futásidőben.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]