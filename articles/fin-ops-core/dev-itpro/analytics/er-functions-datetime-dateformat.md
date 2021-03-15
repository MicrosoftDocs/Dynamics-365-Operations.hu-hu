---
title: DATEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 01/04/2021
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
ms.openlocfilehash: cdc1671f818bc2c4d8a78d0a35337298e83c5060
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/04/2021
ms.locfileid: "4826011"
---
# <a name="dateformat-er-function"></a>DATEFORMAT ER-függvény

[!include [banner](../includes/banner.md)]

A `DATEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Szintaxis 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Argumentumok

`date`: *Dátum*

A formázni kívánt dátumot reprezentáló dátumérték.

`format`: *Karakterlánc*

A kimenő karakterlánc formátuma.

> [!NOTE]
> A formátum-karakterlánc a kis- és nagybetűket megkülönbözteti, ha szabványos vagy egyedi formátumot használ. Például a [szabványos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) „d” formátum a rövid dátumminta alapján adja eredményül a dátumot, míg a szabványos „D” formátum a hosszú dátumminta használatával adja vissza a dátumot. Ezenkívül az [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) „M” formátum a hónapot adja vissza 1 és 12 között, míg az egyéni „m” formátum a percet adja vissza 0 és 59 között.

`culture`: *Karakterlánc*

A formázáshoz használandó területi beállítás.

## <a name="return-values"></a>Visszatérési értékek

*Sztring*

Az eredményül kapott karakterláncérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg. Ha például a `DATEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német kultúra használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német kultúra használatával történik. Az alapértelmezett `culture` érték **EN-US**.

## <a name="example-1"></a>1. példa

A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.

## <a name="example-2"></a>2. példa

A `DATEFORMAT (SESSIONTODAY (), "d", "DE")` az aktuális alkalmazás-munkamenet dátumát adja vissza (2015. december 24.) a **"24-12-2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]