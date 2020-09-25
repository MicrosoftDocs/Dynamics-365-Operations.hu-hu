---
title: DATETIMEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATETIMEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 65b988e6c58aed35577288e01157b8c1f76e6efd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744863"
---
# <a name="datetimeformat-er-function"></a>DATETIMEFORMAT ER-függvény

[!include [banner](../includes/banner.md)]

A `DATETIMEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításokban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Szintaxis 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argumentumok

`datetime`: *DateTime*

A formázására szolgáló dátumot és időpontot jelölő dátum-/időérték.

`format`: *Karakterlánc*

A kimenő karakterlánc formátuma.

`culture`: *Karakterlánc*

A formázáshoz használandó területi beállítás.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott karakterláncérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg. Ha például a `DATETIMEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német területi beállítás használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német területi beállítás használatával történik. Az alapértelmezett `culture` érték **EN-US**.

Amikor a `DATETIMEFORMAT` függvény egy adott dátum-/időértéket konvertál, annak az alkalmazásfelhasználónak az időzóna-beállítását veszi figyelembe, aki azt az ER-formátumot futtatja, amelynek a kontextusában a függvényt hívták.

## <a name="example-1"></a>1. példa

A `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátum-/időértékét, a 2015. december 24-et adja vissza **"24-12-2015"** formában, a megadott egyéni formátum szerint.

## <a name="example-2"></a>2. példa

A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.

## <a name="example-3"></a>3. példa

A `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` a **2019-11-12T08:00:00.0000000-08:00** karakterláncértéket adja eredményül, amikor egy olyan folyamat során hívják meg, amelyet egy olyan alkalmazás kezdeményezett, amelynek a **Nyelvre és országra/régióra vonatkozó beállítások** szakaszában a **(GMT-08:00) Csendes-óceáni idő (Egyesült Államok és Kanada)** érték van megadva.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
