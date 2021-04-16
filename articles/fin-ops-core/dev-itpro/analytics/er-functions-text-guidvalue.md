---
title: GUIDVALUE ER-függvény
description: A témakör tájékoztatást nyújt a GUIDVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746387"
---
# <a name="guidvalue-er-function"></a>GUIDVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `GUIDVALUE` függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja.

## <a name="syntax"></a>Szintaxis

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A *Karakterlánc* típus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*GUID*

Az eredményül kapott globálisan egyedi azonosító (GUID) értéke.

## <a name="usage-notes"></a>Használati megjegyzések

Ellenkező irányú konverzió végrehajtásához (például a *GUID* adattípus megadott bemenetének a egy *Karakterlánc* adattípusú adatelemre konvertálásához) használhatja a [TEXT()](er-functions-text-text.md) függvényt.

## <a name="example"></a>Példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Számított mező* típus **myID** adatforrása, amely a `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")` kifejezést tartalmazza
- A *Táblarekordok* típus **Felhasználók** adatforrása, amely a UserInfo táblára hivatkozik

Ezután használhat olyan kifejezést, mint például a `FILTER (Users, Users.objectId = myID)`, a UserInfo táblának a *GUID* adattípusú **objectId** mező szerinti szűréséhez.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]