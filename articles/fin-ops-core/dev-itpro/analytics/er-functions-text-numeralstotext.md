---
title: NUMERALSTOTEXT ER-függvény
description: A témakör tájékoztatást nyújt a NUMERALSTOTEXT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 459123a66dae7a3d87a22b042e1be6585959ac15
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915625"
---
# <a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `NUMERALSTOTEXT` függvény *Karakterlánc* értékként adja vissza a megadott számot, miután kiírta (azaz szöveges karakterlánccá konvertálta) a megadott nyelven.

## <a name="syntax"></a>Szintaxis

```
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argumentumok

`number`: *Egész* vagy *Valós*

Egy numerikus érték, amely megadja a kiírandó számot.

`language`: *Karakterlánc*

A nyelvkódot jelölő *Karakterlánc* érték.

`currency`: *Karakterlánc*

A pénznemkódot jelölő *Karakterlánc* érték.

`print currency name flag`: *Logikai*

*Logikai* érték, amely azt jelzi, hogy hozzá kell-e adni egy pénznemnevet a kiírt szöveghez.

`decimal points`: *Egész*

Egy *Egész* érték, amely megadja, hogy hány tizedesjegyet kell tartalmaznia a kiírt szövegnek.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A nyelvkód megadása nem kötelező. Ha üres karakterláncként van megadva, akkor a futó környezet nyelvkódját használja a rendszer. Az alapértelmezett nyelvkód az **EN-US**. A futó környezet nyelvkódja az Elektronikus jelentéskészítési (er) formátum **Mappa** vagy **Fájl** elemében van definiálva.

A pénznemkód megadása nem kötelező. Ha üres karakterláncként van megadva, akkor a futó környezet vállalati pénznemét használja a rendszer.

> [!NOTE] 
> A `print currency name flag` és `decimal points` argumentumok csak a következő nyelvkódok esetében kerülnek elemzésre: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** és **RU**. Emellett a `print currency name flag` argumentum elemzését csak azoknak a rendszert használó vállalatoknak az esetében végzi el a rendszer, amelyek ország- vagy régiókörnyezete támogatja a valuták nevének ragozását.

## <a name="example-1"></a>1. példa

A `NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` az **"One Thousand Two Hundred Thirty Four and 56"** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `NUMERALSTOTEXT (120, "PL", "", false, 0)` az **"Sto dwadzieścia"** értéket adja vissza. 

## <a name="example-3"></a>3. példa

A `NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` az **"Сто двадцать евро 21 евроцент"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)