---
title: TRIM ER-függvény
description: Ez a cikk a TRIM Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 02/28/2022
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
ms.openlocfilehash: 95b8d2989d705c4998da0af8e683adf567edfe92
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273098"
---
# <a name="trim-er-function"></a>TRIM ER-függvény

[!include [banner](../includes/banner.md)]

`TRIM` A függvény a megadott szöveg-karakterláncot ad vissza karakterláncként a *lap* után, a szóközök visszaadása, a sorok beszúrása és a képernyő beszúrási karaktere egy karakterrel, a vezető és záró szóközök csonkolása, illetve a szavak közötti szóközök eltávolítása után.

## <a name="syntax"></a>Szintaxis

```vb
TRIM (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

A *Karakterlánc* típus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszatérési értékek

*Sztring*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Bizonyos esetekben előfordulhat, hogy az vezető és záró szóközök csonkolására van szükség, de szeretné a megadott szöveg formázását megtartani. Ha például ez a szöveg olyan címet jelent, amely a többsoros szövegmezőbe írható, és amely tartalmazhatja a beszállítási és a fuvarozási visszáru formázását. Ebben az esetben használja a következő kifejezést: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` hol `text` van az argumentum, amely a megadott szöveges karakterláncra hivatkozik.

## <a name="example-1"></a>1. példa

A `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` a **"Mintaszöveg"** értéket adja vissza.

## <a name="example-2"></a>2. példa

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` A <a0/"Mintaszöveg **" visszaadása**.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[REPLACE ER-függvény](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
