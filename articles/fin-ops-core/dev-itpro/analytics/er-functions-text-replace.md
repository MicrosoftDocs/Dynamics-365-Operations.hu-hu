---
title: REPLACE ER-függvény
description: A témakör tájékoztatást nyújt a REPLACE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916867"
---
# <a name="REPLACE">REPLACE ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `REPLACE` függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal.

## <a name="syntax"></a>Szintaxis

```
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

A *Karakterlánc* típus adatforrásának érvényes elérési útja.

`pattern`: *Karakterlánc*

Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a cserélni kívánt szöveget.

Ha a `regular expression flag` argumentum értéke **IGAZ**, ez az argumentum egy reguláris kifejezést tartalmaz, amely a keresési mintát és a csereszöveget is definiálja.

`replacement`: *Karakterlánc*

Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a csereként használni kívánt szöveget.

Ha a `regular expression flag` argumentum értéke **IGAZ**, ezt az argumentumot nem használja a rendszer.

`regular expression flag`: *Logikai*

*Logikai* érték, amely azt jelzi, hogy a rendszer reguláris kifejezést használ-e a csere során.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a `regular expression flag` argumentum értéke **IGAZ**, ez a függvény a megadott karakterláncot adja vissza a `pattern` argumentum által meghatározott reguláris kifejezés alkalmazásával történt módosítás után. A reguláris kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni.

Ha a `regular expression flag` argumentum **HAMIS**, ez a függvény a [TRANSLATE](er-functions-text-translate.md) függvényhez hasonlóan viselkedik. A `replacement` argumentum által megadott karakterek segítségével ki lehet cserélni a megtalált karaktereket. 

## <a name="example-1"></a>1. példa

A `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` azt a reguláris kifejezést alkalmazza, amely eltávolítja az összes nem numerikus szimbólumot, és **"19234564971"** értéket jelenít meg. 

## <a name="example-2"></a>2. példa

A `REPLACE ("abcdef", "cd", "GH", false)` lecseréli a **"cd"** mintát a **"GH"** karakterláncra, és az **"abGHef"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
